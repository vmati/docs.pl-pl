---
title: Wstawianie obrazu z pliku
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 35900aa2-5615-4174-8212-ba184c6b82fb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a780e35d9eb5420138587102aee753e96a8eff9c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="inserting-an-image-from-a-file"></a><span data-ttu-id="23961-102">Wstawianie obrazu z pliku</span><span class="sxs-lookup"><span data-stu-id="23961-102">Inserting an Image from a File</span></span>
<span data-ttu-id="23961-103">Można napisać dużego obiektu binarnego (BLOB) do bazy danych jako dane binarne lub znaków, w zależności od typu pola w źródle danych.</span><span class="sxs-lookup"><span data-stu-id="23961-103">You can write a binary large object (BLOB) to a database as either binary or character data, depending on the type of field at your data source.</span></span> <span data-ttu-id="23961-104">Obiekt BLOB jest ogólny termin odnoszący się do `text`, `ntext`, i `image` typy danych, które zwykle zawierają dokumenty i obrazy.</span><span class="sxs-lookup"><span data-stu-id="23961-104">BLOB is a generic term that refers to the `text`, `ntext`, and `image` data types, which typically contain documents and pictures.</span></span>  
  
 <span data-ttu-id="23961-105">Można zapisać wartości obiektu BLOB do bazy danych, wykonaj odpowiednie instrukcję INSERT lub UPDATE i przekaż wartość obiektu BLOB jako parametr wejściowy (zobacz [konfigurowania parametrów i typ danych parametru](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)).</span><span class="sxs-lookup"><span data-stu-id="23961-105">To write a BLOB value to your database, issue the appropriate INSERT or UPDATE statement and pass the BLOB value as an input parameter (see [Configuring Parameters and Parameter Data Types](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)).</span></span> <span data-ttu-id="23961-106">Jeśli Twoje obiektów BLOB są przechowywane jako tekst, takich jak SQL Server `text` pola, można przekazać obiektu BLOB jako parametr typu string.</span><span class="sxs-lookup"><span data-stu-id="23961-106">If your BLOB is stored as text, such as a SQL Server `text` field, you can pass the BLOB as a string parameter.</span></span> <span data-ttu-id="23961-107">Jeśli obiekt BLOB jest przechowywany w formacie binarnym, takich jak SQL Server `image` pola, można przekazać tablicy typu `byte` jako parametr binarnego.</span><span class="sxs-lookup"><span data-stu-id="23961-107">If the BLOB is stored in binary format, such as a SQL Server `image` field, you can pass an array of type `byte` as a binary parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23961-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="23961-108">Example</span></span>  
 <span data-ttu-id="23961-109">Poniższy przykładowy kod dodaje informacje dotyczące pracowników do tabeli pracowników w bazie danych Northwind.</span><span class="sxs-lookup"><span data-stu-id="23961-109">The following code example adds employee information to the Employees table in the Northwind database.</span></span> <span data-ttu-id="23961-110">Zdjęcie pracownika jest do odczytu z pliku i dodać do pola zdjęcie w tabeli, która jest pola obrazu.</span><span class="sxs-lookup"><span data-stu-id="23961-110">A photo of the employee is read from a file and added to the Photo field in the table, which is an image field.</span></span>  
  
```vb  
Public Shared Sub AddEmployee( _  
  lastName As String, _  
  firstName As String, _  
  title As String, _  
  hireDate As DateTime, _  
  reportsTo As Integer, _  
  photoFilePath As String, _  
  connectionString As String)  
  
  Dim photo() as Byte = GetPhoto(photoFilePath)  
  
  Using connection As SqlConnection = New SqlConnection( _  
    connectionString)  
  
  Dim command As SqlCommand = New SqlCommand( _  
    "INSERT INTO Employees (LastName, FirstName, Title, " & _  
    "HireDate, ReportsTo, Photo) " & _  
    "Values(@LastName, @FirstName, @Title, " & _  
    "@HireDate, @ReportsTo, @Photo)", connection)   
  
  command.Parameters.Add("@LastName",  _  
    SqlDbType.NVarChar, 20).Value = lastName  
  command.Parameters.Add("@FirstName", _  
    SqlDbType.NVarChar, 10).Value = firstName  
  command.Parameters.Add("@Title", _  
    SqlDbType.NVarChar, 30).Value = title  
  command.Parameters.Add("@HireDate", _  
    SqlDbType.DateTime).Value = hireDate  
  command.Parameters.Add("@ReportsTo", _  
    SqlDbType.Int).Value = reportsTo  
  
  command.Parameters.Add("@Photo", _  
    SqlDbType.Image, photo.Length).Value = photo  
  
  connection.Open()  
  command.ExecuteNonQuery()  
  
  End Using  
End Sub  
  
Public Shared Function GetPhoto(filePath As String) As Byte()  
  Dim stream As FileStream = new FileStream( _  
     filePath, FileMode.Open, FileAccess.Read)  
  Dim reader As BinaryReader = new BinaryReader(stream)  
  
  Dim photo() As Byte = reader.ReadBytes(stream.Length)  
  
  reader.Close()  
  stream.Close()  
  
  Return photo  
End Function  
```  
  
```csharp  
public static void AddEmployee(  
  string lastName,   
  string firstName,   
  string title,   
  DateTime hireDate,   
  int reportsTo,   
  string photoFilePath,   
  string connectionString)  
{  
  byte[] photo = GetPhoto(photoFilePath);  
  
  using (SqlConnection connection = new SqlConnection(  
    connectionString))  
  
  SqlCommand command = new SqlCommand(  
    "INSERT INTO Employees (LastName, FirstName, " +  
    "Title, HireDate, ReportsTo, Photo) " +  
    "Values(@LastName, @FirstName, @Title, " +  
    "@HireDate, @ReportsTo, @Photo)", connection);   
  
  command.Parameters.Add("@LastName",    
     SqlDbType.NVarChar, 20).Value = lastName;  
  command.Parameters.Add("@FirstName",   
      SqlDbType.NVarChar, 10).Value = firstName;  
  command.Parameters.Add("@Title",       
      SqlDbType.NVarChar, 30).Value = title;  
  command.Parameters.Add("@HireDate",   
       SqlDbType.DateTime).Value = hireDate;  
  command.Parameters.Add("@ReportsTo",   
      SqlDbType.Int).Value = reportsTo;  
  
  command.Parameters.Add("@Photo",  
      SqlDbType.Image, photo.Length).Value = photo;  
  
  connection.Open();  
  command.ExecuteNonQuery();  
  }  
}  
  
public static byte[] GetPhoto(string filePath)  
{  
  FileStream stream = new FileStream(  
      filePath, FileMode.Open, FileAccess.Read);  
  BinaryReader reader = new BinaryReader(stream);  
  
  byte[] photo = reader.ReadBytes((int)stream.Length);  
  
  reader.Close();  
  stream.Close();  
  
  return photo;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="23961-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="23961-111">See Also</span></span>  
 [<span data-ttu-id="23961-112">Aby zmodyfikować danych za pomocą poleceń</span><span class="sxs-lookup"><span data-stu-id="23961-112">Using Commands to Modify Data</span></span>](../../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 [<span data-ttu-id="23961-113">Podczas pobierania danych binarnych</span><span class="sxs-lookup"><span data-stu-id="23961-113">Retrieving Binary Data</span></span>](../../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 [<span data-ttu-id="23961-114">Dane binarne i duża wartość serwera SQL</span><span class="sxs-lookup"><span data-stu-id="23961-114">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="23961-115">Mapowanie typu danych serwera SQL</span><span class="sxs-lookup"><span data-stu-id="23961-115">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="23961-116">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="23961-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
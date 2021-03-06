---
title: "polecenie odwołania Usuń DotNet - .NET Core interfejsu wiersza polecenia"
description: "Polecenie dotnet Usuń odwołanie zapewnia to wygodny sposób, aby usunąć odwołania projektu do projektu."
keywords: "Usuń DotNet, interfejsu wiersza polecenia, polecenia interfejsu wiersza polecenia, .NET Core"
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 691fd77c7605b6476adc764f20e59b51abd7d914
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-remove-reference"></a>DotNet Usuń odwołanie

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Nazwa

`dotnet remove reference`— Usuwa odwołania projektu do projektu.

## <a name="synopsis"></a>Streszczenie

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Opis

`dotnet remove reference` Polecenie zapewnia to wygodny sposób, aby usunąć odwołania do projektu z projektu.

## <a name="arguments"></a>Argumenty

`PROJECT`

Docelowy plik projektu. Jeśli nie zostanie określony, polecenie wyszukuje w bieżącym katalogu dla jednego.

`PROJECT_REFERENCES`

Projekt do projektu (P2P odwołania do usunięcia. Można określić jedną lub wiele projektów. [Wzorce glob](https://en.wikipedia.org/wiki/Glob_(programming)) są obsługiwane w terminali z systemem Unix/Linux.

## <a name="options"></a>Opcje

`-h|--help`

Drukuje krótkich pomocy dla polecenia.

`-f|--framework <FRAMEWORK>`

Usuwa odwołanie tylko wtedy, gdy przeznaczonych dla określonej [framework](../../standard/frameworks.md).

## <a name="examples"></a>Przykłady

Usuń odwołanie do projektu z określonego projektu:

`dotnet remove app/app.csproj reference lib/lib.csproj`

Usuń wiele odwołań do projektu z projektu w bieżącym katalogu:

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

Usuń wiele odwołań do projektu przy użyciu wzorca glob w systemie Unix/Linux:

`dotnet remove app/app.csproj reference **/*.csproj`

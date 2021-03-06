# [Windows Workflow Foundation](index.md)
## [Przewodnik po dokumentacji programu Windows Workflow](guide-to-the-documentation.md)
## [Co nowego w programie Windows Workflow Foundation](whats-new.md)
## [Co nowego w programie Windows Workflow Foundation na platformie .NET 4.5](whats-new-in-wf-in-dotnet.md)
## [Przestarzałe typy w programie Windows Workflow Foundation](deprecated-types.md)
## [Charakterystyka funkcji programu Windows Workflow Foundation](feature-specifics.md)
## [Omówienie pojęć związanych z programem Windows Workflow](conceptual-overview.md)
### [Omówienie programu Windows Workflow](overview.md)
### [Podstawowe pojęcia związane z programem Windows Workflow](fundamental-concepts.md)
### [Architektura programu Windows Workflow](architecture.md)
## [Wprowadzenie — samouczek](getting-started-tutorial.md)
### [Instrukcje: Tworzenie działania](how-to-create-an-activity.md)
### [Instrukcje: Tworzenie przepływu pracy](how-to-create-a-workflow.md)
#### [Instrukcje: Tworzenie przepływu pracy schematu blokowego](how-to-create-a-flowchart-workflow.md)
#### [Instrukcje: Tworzenie sekwencyjnego przepływu pracy](how-to-create-a-sequential-workflow.md)
#### [Instrukcje: Tworzenie przepływu pracy automatu stanów](how-to-create-a-state-machine-workflow.md)
### [Instrukcje: Uruchamianie przepływu pracy](how-to-run-a-workflow.md)
### [Instrukcje: Tworzenie i uruchamianie długotrwałego przepływu pracy](how-to-create-and-run-a-long-running-workflow.md)
### [Instrukcje: Tworzenie niestandardowego uczestnika śledzenia](how-to-create-a-custom-tracking-participant.md)
### [Instrukcje: Równoczesne hostowanie wielu wersji przepływu pracy](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)
### [Instrukcje: Aktualizowanie definicji działającego wystąpienia przepływu pracy](how-to-update-the-definition-of-a-running-workflow-instance.md)
## [Programowanie w programie Windows Workflow Foundation](programming.md)
### [Projektowanie przepływów pracy](designing-workflows.md)
#### [Przepływy pracy schematów blokowych](flowchart-workflows.md)
#### [Proceduralne przepływy pracy](procedural-workflows.md)
#### [Przepływy pracy automatu stanów](state-machine-workflows.md)
#### [Tworzenie przepływów pracy, działań i wyrażeń przy użyciu kodu imperatywnego](authoring-workflows-activities-and-expressions-using-imperative-code.md)
### [Używanie i tworzenie działań](using-and-creating-activities.md)
#### [Wbudowana biblioteka działań](net-framework-4-5-built-in-activity-library.md)
##### [Przepływ sterowania](control-flow-activities-in-wf.md)
###### [Wybieranie działania](pick-activity.md)
##### [Schemat blokowy](flowchart-activities-in-wf.md)
##### [Automat stanów](state-machine-activities-in-wf.md)
##### [Środowisko uruchomieniowe](runtime-activities-in-wf.md)
##### [Typy pierwotne](primitives-activities-in-wf.md)
##### [Transakcja](transaction-activities-in-wf.md)
##### [Kolekcja](collection-activities-in-wf.md)
##### [Obsługa błędów](error-handling-activities-in-wf.md)
##### [Migracja](migration-activity-in-wf.md)
#### [Projektowanie i implementowanie niestandardowych działań](designing-and-implementing-custom-activities.md)
##### [Opcje tworzenia działań](activity-authoring-options-in-wf.md)
###### [Klasa bazowa Activity](workflow-activity-authoring-using-the-activity-class.md)
###### [Klasa bazowa CodeActivity](workflow-activity-authoring-using-the-codeactivity-class.md)
###### [Klasa bazowa NativeActivity](nativeactivity-base-class.md)
##### [Używanie niestandardowego działania](using-a-custom-activity.md)
##### [Tworzenie działań asynchronicznych](creating-asynchronous-activities-in-wf.md)
###### [Obsługa błędów w działaniach asynchronicznych](error-handling-in-asynchronous-activities.md)
##### [Konfigurowanie walidacji działania](configuring-activity-validation.md)
###### [Wymagane argumenty i grupy metod przeciążonych](required-arguments-and-overload-groups.md)
###### [Walidacja oparta na kodzie imperatywnym](imperative-code-based-validation.md)
###### [Ograniczenia deklaratywne](declarative-constraints.md)
###### [Wywoływanie walidacji działania](invoking-activity-validation.md)
##### [Tworzenie działania w środowisku uruchomieniowym](creating-an-activity-at-runtime-with-dynamicactivity.md)
##### [Właściwości wykonania przepływu pracy](workflow-execution-properties.md)
##### [Używanie delegatów działania](using-activity-delegates.md)
##### [Lokalizacja działania](activity-localization.md)
##### [Używanie rozszerzeń działania](using-activity-extensions.md)
##### [Wykorzystywanie źródeł strumieniowych danych OData z przepływu pracy](consuming-odata-feeds-from-a-workflow.md)
##### [Wyznaczanie zakresu i widoczność definicji działania](activity-definition-scoping-and-visibility.md)
##### [Tworzenie niestandardowych działań sterowania przepływem](creating-custom-flow-control-activities.md)
### [Model danych programu Windows Workflow Foundation](data-model.md)
#### [Zmienne i argumenty](variables-and-arguments.md)
#### [Wyrażenia](expressions.md)
#### [Wyrażenia języka C#](csharp-expressions.md)
#### [Właściwości a argumenty](properties-vs-arguments.md)
#### [Uwidacznianie danych przy użyciu metody CacheMetadata](exposing-data-with-cachemetadata.md)
### [Oczekiwanie na dane wejściowe w przepływie pracy](waiting-for-input-in-a-workflow.md)
#### [Zakładki](bookmarks.md)
### [Wyjątki, transakcje i kompensacja](exceptions-transactions-and-compensation.md)
#### [Wyjątki](exceptions.md)
#### [Transakcje](workflow-transactions.md)
#### [Kompensacja](compensation.md)
#### [Anulowanie](modeling-cancellation-behavior-in-workflows.md)
#### [Debugowanie przepływów pracy](debugging-workflows.md)
### [Hostowanie przepływów pracy](hosting-workflows.md)
#### [Opcje hostowania przepływu pracy](workflow-hosting-options.md)
#### [Używanie obiektu WorkflowInvoker i WorkflowApplication](using-workflowinvoker-and-workflowapplication.md)
#### [Kontrola drzewa działań](activity-tree-inspection.md)
#### [Serializowanie przepływów pracy i działań do i z plików XAML](serializing-workflows-and-activities-to-and-from-xaml.md)
#### [Używanie obiektu WorkflowIdentity i wersjonowanie](using-workflowidentity-and-versioning.md)
### [Aktualizacja dynamiczna](dynamic-update.md)
### [Programowanie usługi przepływu pracy narzędzia Contract-First](contract-first-workflow-service-development.md)
### [Instrukcje: Tworzenie usługi przepływu pracy wykorzystującej istniejący kontrakt usługi](how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
### [Trwałość przepływu pracy](workflow-persistence.md)
#### [Magazyn wystąpień przepływu pracy SQL](sql-workflow-instance-store.md)
##### [Właściwości magazynu wystąpień przepływu pracy SQL](properties-of-sql-workflow-instance-store.md)
###### [Opcja kodowania wystąpienia](instance-encoding-option.md)
###### [Działanie ukończenia wystąpienia](instance-completion-action.md)
###### [Działanie zablokowanego wyjątku wystąpienia](instance-locked-exception-action.md)
###### [Okres odnowienia blokady hosta](host-lock-renewal-period.md)
###### [Okres wykrywania wystąpień możliwych do uruchomienia](runnable-instances-detection-period.md)
###### [Parametry połączenia i nazwa parametrów połączenia](connection-string-and-connection-string-name.md)
##### [Instrukcje: Włączanie stanów trwałych programu SQL dla przepływów pracy i usług przepływu pracy](how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)
##### [Aktywacja wystąpienia](instance-activation.md)
##### [Obsługa zapytań](support-for-queries.md)
##### [Rozszerzalność magazynu](store-extensibility.md)
##### [Zabezpieczenia](security.md)
##### [Baza danych stanów trwałych programu SQL Server](sql-server-persistence-database.md)
###### [Schemat bazy danych stanów trwałych](persistence-database-schema.md)
###### [Instrukcje: Deserializacja właściwości danych wystąpienia](how-to-deserialize-instance-data-properties.md)
###### [Instrukcje: Zapytanie dotyczące wystąpień nietrwałych](how-to-query-for-non-persisted-instances.md)
#### [Magazyny wystąpień](instance-stores.md)
##### [Instrukcje: Włączanie stanów trwałych dla przepływów pracy i usług przepływu pracy](how-to-enable-persistence-for-workflows-and-workflow-services.md)
##### [Instrukcje: Tworzenie niestandardowego magazynu wystąpień](how-to-create-a-custom-instance-store.md)
#### [Uczestnicy stanów trwałych](persistence-participants.md)
##### [Instrukcje: Tworzenie niestandardowego uczestnika stanów trwałych](how-to-create-a-custom-persistence-participant.md)
#### [Najlepsze rozwiązania w zakresie stanów trwałych](persistence-best-practices.md)
#### [Nietrwałe wystąpienia przepływu pracy](non-persisted-workflow-instances.md)
#### [Wstrzymywanie i wznawianie przepływu pracy](pausing-and-resuming-a-workflow.md)
### [Wskazówki dotyczące migracji](wf-migration-guidance.md)
#### [Wskazówki dotyczące migracji](migration-guidance.md)
#### [Używanie działań WF programu .NET Framework 3.0 w .NET Framework 4 przy użyciu działań Interop](net-framework-3-0-wf-in-net-framework-4-interop.md)
#### [Używanie działania Interop w przepływie pracy programu .NET Framework 4](using-the-interop-activity-in-a-net-framework-4-workflow.md)
#### [Pisanie projektów przeznaczonych dla programu .NET Framework 3.0 i 3.5 w programie Visual Studio 2010](projects-targeting-dotnet-in-vs.md)
### [Kontrola i śledzenie przepływu pracy](workflow-tracking-and-tracing.md)
#### [Rekordy śledzenia](tracking-records.md)
#### [Profile śledzenia](tracking-profiles.md)
#### [Uczestnicy śledzenia](tracking-participants.md)
#### [Konfigurowanie śledzenia dla przepływu pracy](configuring-tracking-for-a-workflow.md)
#### [Używanie śledzenia do rozwiązywania problemów z aplikacjami](using-tracking-to-troubleshoot-applications.md)
#### [Śledzenie przepływu pracy](workflow-tracing.md)
#### [Dokumentacja zdarzeń śledzenia](tracking-events-reference.md)
##### [100 — WorkflowInstanceRecord](100-workflowinstancerecord.md)
##### [101 — WorkflowInstanceUnhandledExceptionRecord](101-workflowinstanceunhandledexceptionrecord.md)
##### [102 — WorkflowInstanceAbortedRecord](102-workflowinstanceabortedrecord.md)
##### [103 — ActivityStateRecord](103-activitystaterecord.md)
##### [104 — ActivityScheduledRecord](104-activityscheduledrecord.md)
##### [105 — FaultPropagationRecord](105-faultpropagationrecord.md)
##### [106 — CancelRequestRecord](106-cancelrequestrecord.md)
##### [107 — BookmarkResumptionRecord](107-bookmarkresumptionrecord.md)
##### [108 — CustomTrackingRecordInfo](108-customtrackingrecordinfo.md)
##### [110 — CustomTrackingRecordWarning](110-customtrackingrecordwarning.md)
##### [111 — CustomTrackingRecordError](111-customtrackingrecorderror.md)
##### [112 — WorkflowInstanceSuspendedRecord](112-workflowinstancesuspendedrecord.md)
##### [113 — WorkflowInstanceTerminatedRecord](113-workflowinstanceterminatedrecord.md)
##### [114 — WorkflowInstanceRecordWithId](114-workflowinstancerecordwithid.md)
##### [115 — WorkflowInstanceAbortedRecordWithId](115-workflowinstanceabortedrecordwithid.md)
##### [116 — WorkflowInstanceSuspendedRecordWithId](116-workflowinstancesuspendedrecordwithid.md)
##### [117 — WorkflowInstanceTerminatedRecordWithId](117-workflowinstanceterminatedrecordwithid.md)
##### [118 — WorkflowInstanceUnhandledExceptionRecordWithId](118-workflowinstanceunhandledexceptionrecordwithid.md)
##### [119 — WorkflowInstanceUpdatedRecord](119-workflowinstanceupdatedrecord.md)
##### [225 — TraceCorrelationKeys](225-tracecorrelationkeys.md)
##### [440 — StartSignpostEvent1](440-startsignpostevent.md)
##### [441 — StopSignpostEvent1](441-stopsignpostevent.md)
##### [1001 — WorkflowApplicationCompleted](1001-workflowapplicationcompleted.md)
##### [1002 — WorkflowApplicationTerminated](1002-workflowapplicationterminated.md)
##### [1003 — WorkflowInstanceCanceled](1003-workflowinstancecanceled.md)
##### [1004 — WorkflowInstanceAborted](1004-workflowinstanceaborted.md)
##### [1005 — WorkflowApplicationIdled](1005-workflowapplicationidled.md)
##### [1006 — WorkflowApplicationUnhandledException](1006-workflowapplicationunhandledexception.md)
##### [1007 — WorkflowApplicationPersisted](1007-workflowapplicationpersisted.md)
##### [1008 — WorkflowApplicationUnloaded](1008-workflowapplicationunloaded.md)
##### [1009 — ActivityScheduled](1009-activityscheduled.md)
##### [1010 — ActivityCompleted](1010-activitycompleted.md)
##### [1011 — ScheduleExecuteActivityWorkItem](1011-scheduleexecuteactivityworkitem.md)
##### [1012 — StartExecuteActivityWorkItem](1012-startexecuteactivityworkitem.md)
##### [1013 — CompleteExecuteActivityWorkItem](1013-completeexecuteactivityworkitem.md)
##### [1014 — ScheduleCompletionWorkItem](1014-schedulecompletionworkitem.md)
##### [1015 — StartCompletionWorkItem](1015-startcompletionworkitem.md)
##### [1016 — CompleteCompletionWorkItem](1016-completecompletionworkitem.md)
##### [1017 — ScheduleCancelActivityWorkItem](1017-schedulecancelactivityworkitem.md)
##### [1018 — StartCancelActivityWorkItem](1018-startcancelactivityworkitem.md)
##### [1019 — CompleteCancelActivityWorkItem](1019-completecancelactivityworkitem.md)
##### [1020 — CreateBookmark](1020-createbookmark.md)
##### [1021 — ScheduleBookmarkWorkItem](1021-schedulebookmarkworkitem.md)
##### [1022 — StartBookmarkWorkItem](1022-startbookmarkworkitem.md)
##### [1023 — CompleteBookmarkWorkItem](1023-completebookmarkworkitem.md)
##### [1024 — CreateBookmarkScope](1024-createbookmarkscope.md)
##### [1025 — BookmarkScopeInitialized](1025-bookmarkscopeinitialized.md)
##### [1026 — ScheduleTransactionContextWorkItem](1026-scheduletransactioncontextworkitem.md)
##### [1027 — StartTransactionContextWorkItem](1027-starttransactioncontextworkitem.md)
##### [1028 — CompleteTransactionContextWorkItem](1028-completetransactioncontextworkitem.md)
##### [1029 — ScheduleFaultWorkItem](1029-schedulefaultworkitem.md)
##### [1030 — StartFaultWorkItem](1030-startfaultworkitem.md)
##### [1031 — CompleteFaultWorkItem](1031-completefaultworkitem.md)
##### [1032 — ScheduleRuntimeWorkItem](1032-scheduleruntimeworkitem.md)
##### [1033 — StartRuntimeWorkItem](1033-startruntimeworkitem.md)
##### [1034 — CompleteRuntimeWorkItem](1034-completeruntimeworkitem.md)
##### [1035 — RuntimeTransactionSet](1035-runtimetransactionset.md)
##### [1036 — RuntimeTransactionCompletionRequested](1036-runtimetransactioncompletionrequested.md)
##### [1037 — RuntimeTransactionComplete](1037-runtimetransactioncomplete.md)
##### [1038 — EnterNoPersistBlock](1038-enternopersistblock.md)
##### [1039 — ExitNoPersistBlock](1039-exitnopersistblock.md)
##### [1040 — InArgumentBound](1040-inargumentbound.md)
##### [1041 — WorkflowApplicationPersistableIdle](1041-workflowapplicationpersistableidle.md)
##### [1101 — WorkflowActivityStart](1101-workflowactivitystart.md)
##### [1102 — WorkflowActivityStop](1102-workflowactivitystop.md)
##### [1103 — WorkflowActivitySuspend](1103-workflowactivitysuspend.md)
##### [1104 — WorkflowActivityResume](1104-workflowactivityresume.md)
##### [1124 — InvokeMethodIsStatic](1124-invokemethodisstatic.md)
##### [1125 — InvokeMethodIsNotStatic](1125-invokemethodisnotstatic.md)
##### [1126 — InvokedMethodThrewException](1126-invokedmethodthrewexception.md)
##### [1131 — InvokeMethodUseAsyncPattern](1131-invokemethoduseasyncpattern.md)
##### [1132 — InvokeMethodDoesNotUseAsyncPattern](1132-invokemethoddoesnotuseasyncpattern.md)
##### [1140 — FlowchartStart](1140-flowchartstart.md)
##### [1141 — FlowchartEmpty](1141-flowchartempty.md)
##### [1143 — FlowchartNextNull](1143-flowchartnextnull.md)
##### [1146 — FlowchartSwitchCase](1146-flowchartswitchcase.md)
##### [1147 — FlowchartSwitchDefault](1147-flowchartswitchdefault.md)
##### [1148 — FlowchartSwitchCaseNotFound](1148-flowchartswitchcasenotfound.md)
##### [1150 — CompensationState](1150-compensationstate.md)
##### [1223 — SwitchCaseNotFound](1223-switchcasenotfound.md)
##### [1449 — WfMessageReceived](1449-wfmessagereceived.md)
##### [1450 — WfMessageSent](1450-wfmessagesent.md)
##### [2021 — ExecuteWorkItemStart](2021-executeworkitemstart.md)
##### [2022 — ExecuteWorkItemStop](2022-executeworkitemstop.md)
##### [2023 — SendMessageChannelCacheMiss](2023-sendmessagechannelcachemiss.md)
##### [2024 — InternalCacheMetadataStart](2024-internalcachemetadatastart.md)
##### [2025 — InternalCacheMetadataStop](2025-internalcachemetadatastop.md)
##### [2026 — CompileVbExpressionStart](2026-compilevbexpressionstart.md)
##### [2027 — CacheRootMetadataStart](2027-cacherootmetadatastart.md)
##### [2028 — CacheRootMetadataStop](2028-cacherootmetadatastop.md)
##### [2029 — CompileVbExpressionStop](2029-compilevbexpressionstop.md)
##### [2576 — TryCatchExceptionFromTry](2576-trycatchexceptionfromtry.md)
##### [2577 — TryCatchExceptionDuringCancelation](2577-trycatchexceptionduringcancelation.md)
##### [2578 — TryCatchExceptionFromCatchOrFinally](2578-trycatchexceptionfromcatchorfinally.md)
##### [3501 — InferredContractDescription](3501-inferredcontractdescription.md)
##### [3502 — InferredOperationDescription](3502-inferredoperationdescription.md)
##### [3503 — DuplicateCorrelationQuery](3503-duplicatecorrelationquery.md)
##### [3507 — ServiceEndpointAdded](3507-serviceendpointadded.md)
##### [3508 — TrackingProfileNotFound](3508-trackingprofilenotfound.md)
##### [3550 — BufferOutOfOrderMessageNoInstance](3550-bufferoutofordermessagenoinstance.md)
##### [3551 — BufferOutOfOrderMessageNoBookmark](3551-bufferoutofordermessagenobookmark.md)
##### [3552 — MaxPendingMessagesPerChannelExceeded](3552-maxpendingmessagesperchannelexceeded.md)
##### [3557 — TransactedReceiveScopeEndCommitFailed](3557-transactedreceivescopeendcommitfailed.md)
##### [4201 — EndSqlCommandExecute](4201-endsqlcommandexecute.md)
##### [4202 — StartSqlCommandExecute](4202-startsqlcommandexecute.md)
##### [4203 — RenewLockSystemError](4203-renewlocksystemerror.md)
##### [4205 — FoundProcessingError](4205-foundprocessingerror.md)
##### [4206 — UnlockInstanceException](4206-unlockinstanceexception.md)
##### [4207 — MaximumRetriesExceededForSqlCommand](4207-maximumretriesexceededforsqlcommand.md)
##### [4208 — RetryingSqlCommandDueToSqlError](4208-retryingsqlcommandduetosqlerror.md)
##### [4209 — TimeoutOpeningSqlConnection](4209-timeoutopeningsqlconnection.md)
##### [4210 — SqlExceptionCaught](4210-sqlexceptioncaught.md)
##### [4211 — QueuingSqlRetry](4211-queuingsqlretry.md)
##### [4212 — LockRetryTimeout](4212-lockretrytimeout.md)
##### [4213 — RunnableInstancesDetectionError](4213-runnableinstancesdetectionerror.md)
##### [4214 — InstanceLocksRecoveryError](4214-instancelocksrecoveryerror.md)
##### [39456 — TrackingRecordDropped](39456-trackingrecorddropped.md)
##### [39457 — TrackingRecordRaised](39457-trackingrecordraised.md)
##### [39458 — TrackingRecordTruncated](39458-trackingrecordtruncated.md)
##### [39459 — TrackingDataExtracted](39459-trackingdataextracted.md)
##### [39460 — TrackingValueNotSerializable](39460-trackingvaluenotserializable.md)
##### [57398 — MaxInstancesExceeded](57398-maxinstancesexceeded.md)
#### [Niestandardowe rekordy śledzenia](custom-tracking-records.md)
#### [Śledzenie argumentów i zmiennych](variable-and-argument-tracking.md)
#### [Określanie czasu trwania wykonania przepływu pracy za pomocą śledzenia](determining-workflow-execution-duration-using-tracing.md)
### [Zabezpieczenia przepływu pracy](workflow-security.md)
### [Wydajność programu Windows Workflow Foundation 4](performance.md)
## [Rozszerzanie programu Windows Workflow Foundation](extend.md)
### [Dostosowywanie środowiska projektowania przepływu pracy](customizing-the-workflow-design-experience.md)
#### [Używanie niestandardowych szablonów i projektantów działań](using-custom-activity-designers-and-templates.md)
##### [Instrukcje: Tworzenie niestandardowego projektanta działań](how-to-create-a-custom-activity-designer.md)
##### [Instrukcje: Tworzenie niestandardowego szablonu działań](how-to-create-a-custom-activity-template.md)
##### [Używanie kontekstu edycyjnego ModelItem](using-the-modelitem-editing-context.md)
##### [Powiązanie niestandardowych właściwości działań z kontrolką projektanta](binding-a-custom-activity-property-to-a-designer-control.md)
#### [Rehostowanie projektanta przepływu pracy](rehosting-the-workflow-designer.md)
##### [Zadanie 1: Tworzenie nowej aplikacji Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)
##### [Zadanie 2: Hostowanie projektanta przepływu pracy](task-2-host-the-workflow-designer.md)
##### [Zadanie 3: Tworzenie okienka PropertyGrid i przybornika](task-3-create-the-toolbox-and-propertygrid-panes.md)
##### [Instrukcje: Wyświetlanie błędów walidacji w rehostowanym projektancie](how-to-display-validation-errors-in-a-rehosted-designer.md)
##### [Obsługa nowych funkcji w programie Workflow Foundation 4.5 w rehostowanym projektancie przepływu pracy](wf-features-in-the-rehosted-workflow-designer.md)
#### [Używanie edytora wyrażeń niestandardowych](using-a-custom-expression-editor.md)
## [Słownik programu Windows Workflow Foundation](glossary.md)
## [Przykłady Windows Workflow](samples/)

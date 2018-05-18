# [Kernel Transaction Manager](kernel-transaction-manager-portal.md)
## [About KTM](about-ktm.md)
### [What is a Transaction?](what-is-a-transaction.md)
### [Working With Transactions](programming-model.md)
#### [Transactions](transactions.md)
### [Writing a Resource Manager](writing-a-resource-manager.md)
#### [Transaction Managers](transaction-managers.md)
#### [Resource Managers](resource-managers.md)
#### [Enlistments](enlistments.md)
#### [Recovery Processing](recovery-processing.md)
#### [Programming Considerations For Writing Resource Managers](programming-considerations.md)
### [Interoperability With Other Windows Features](interoperability-with-other-windows-features.md)
### [KTM Security and Access Rights](ktm-security-and-access-rights.md)
## [KTM Reference](ktm-reference.md)
### [Kernel Transaction Manager Enumerations](kernel-transaction-manager-enumerations.md)
#### [TRANSACTION_OUTCOME](/windows/win32/content/Winnt/ne-winnt-_transaction_outcome?branch=dev)
### [Kernel Transaction Manager Functions](kernel-transaction-manager-functions.md)
#### [CommitComplete](/windows/win32/content/Ktmw32/nf-ktmw32-commitcomplete?branch=dev)
#### [CommitEnlistment](/windows/win32/content/KtmW32/nf-ktmw32-commitenlistment?branch=dev)
#### [CommitTransaction](/windows/win32/content/Ktmw32/nf-ktmw32-committransaction?branch=dev)
#### [CommitTransactionAsync](/windows/win32/content/Ktmw32/nf-ktmw32-committransactionasync?branch=dev)
#### [CreateEnlistment](/windows/win32/content/KtmW32/nf-ktmw32-createenlistment?branch=dev)
#### [CreateResourceManager](/windows/win32/content/Ktmw32/nf-ktmw32-createresourcemanager?branch=dev)
#### [CreateTransaction](/windows/win32/content/KtmW32/nf-ktmw32-createtransaction?branch=dev)
#### [CreateTransactionManager](/windows/win32/content/Ktmw32/nf-ktmw32-createtransactionmanager?branch=dev)
#### [GetCurrentClockTransactionManager](/windows/win32/content/Ktmw32/nf-ktmw32-getcurrentclocktransactionmanager?branch=dev)
#### [GetEnlistmentId](/windows/win32/content/Ktmw32/nf-ktmw32-getenlistmentid?branch=dev)
#### [GetEnlistmentRecoveryInformation](/windows/win32/content/Ktmw32/nf-ktmw32-getenlistmentrecoveryinformation?branch=dev)
#### [GetNotificationResourceManager](/windows/win32/content/KtmW32/nf-ktmw32-getnotificationresourcemanager?branch=dev)
#### [GetNotificationResourceManagerAsync](/windows/win32/content/KtmW32/nf-ktmw32-getnotificationresourcemanagerasync?branch=dev)
#### [GetTransactionId](/windows/win32/content/Ktmw32/nf-ktmw32-gettransactionid?branch=dev)
#### [GetTransactionInformation](/windows/win32/content/Ktmw32/nf-ktmw32-gettransactioninformation?branch=dev)
#### [GetTransactionManagerId](/windows/win32/content/Ktmw32/nf-ktmw32-gettransactionmanagerid?branch=dev)
#### [OpenEnlistment](/windows/win32/content/Ktmw32/nf-ktmw32-openenlistment?branch=dev)
#### [OpenResourceManager](/windows/win32/content/Ktmw32/nf-ktmw32-openresourcemanager?branch=dev)
#### [OpenTransaction](/windows/win32/content/Ktmw32/nf-ktmw32-opentransaction?branch=dev)
#### [OpenTransactionManager](/windows/win32/content/Ktmw32/nf-ktmw32-opentransactionmanager?branch=dev)
#### [OpenTransactionManagerById](/windows/win32/content/Ktmw32/nf-ktmw32-opentransactionmanagerbyid?branch=dev)
#### [PrepareComplete](/windows/win32/content/Ktmw32/nf-ktmw32-preparecomplete?branch=dev)
#### [PrepareEnlistment](/windows/win32/content/KtmW32/nf-ktmw32-prepareenlistment?branch=dev)
#### [PrePrepareComplete](/windows/win32/content/Ktmw32/nf-ktmw32-prepreparecomplete?branch=dev)
#### [PrePrepareEnlistment](/windows/win32/content/KtmW32/nf-ktmw32-preprepareenlistment?branch=dev)
#### [ReadOnlyEnlistment](/windows/win32/content/Ktmw32/nf-ktmw32-readonlyenlistment?branch=dev)
#### [RecoverEnlistment](/windows/win32/content/Ktmw32/nf-ktmw32-recoverenlistment?branch=dev)
#### [RecoverResourceManager](/windows/win32/content/Ktmw32/nf-ktmw32-recoverresourcemanager?branch=dev)
#### [RecoverTransactionManager](/windows/win32/content/Ktmw32/nf-ktmw32-recovertransactionmanager?branch=dev)
#### [RenameTransactionManager](/windows/win32/content/KtmW32/nf-ktmw32-renametransactionmanager?branch=dev)
#### [RollbackComplete](/windows/win32/content/Ktmw32/nf-ktmw32-rollbackcomplete?branch=dev)
#### [RollbackEnlistment](/windows/win32/content/Ktmw32/nf-ktmw32-rollbackenlistment?branch=dev)
#### [RollbackTransaction](/windows/win32/content/Ktmw32/nf-ktmw32-rollbacktransaction?branch=dev)
#### [RollbackTransactionAsync](/windows/win32/content/Ktmw32/nf-ktmw32-rollbacktransactionasync?branch=dev)
#### [RollforwardTransactionManager](/windows/win32/content/KtmW32/nf-ktmw32-rollforwardtransactionmanager?branch=dev)
#### [SetEnlistmentRecoveryInformation](/windows/win32/content/Ktmw32/nf-ktmw32-setenlistmentrecoveryinformation?branch=dev)
#### [SetResourceManagerCompletionPort](/windows/win32/content/Ktmw32/nf-ktmw32-setresourcemanagercompletionport?branch=dev)
#### [SetTransactionInformation](/windows/win32/content/Ktmw32/nf-ktmw32-settransactioninformation?branch=dev)
#### [SinglePhaseReject](/windows/win32/content/Ktmw32/nf-ktmw32-singlephasereject?branch=dev)
### [Kernel Transaction Manager Structures](kernel-transaction-manager-structures.md)
#### [TRANSACTION_NOTIFICATION](/windows/win32/content/KtmTypes/ns-ktmtypes-_transaction_notification?branch=dev)
#### [TRANSACTION_NOTIFICATION_RECOVERY_ARGUMENT](/windows/win32/content/KtmTypes/ns-ktmtypes-_transaction_notification_recovery_argument?branch=dev)
### [Kernel Transaction Manager Constants](kernel-transaction-manager-constants.md)
#### [Enlistment Access Masks](enlistment-access-masks.md)
#### [NOTIFICATION_MASK](notification-mask.md)
#### [Resource Manager Access Masks](resource-manager-access-masks.md)
#### [Transaction Access Masks](transaction-access-masks.md)
#### [Transaction Manager Access Masks](transaction-manager-access-masks.md)

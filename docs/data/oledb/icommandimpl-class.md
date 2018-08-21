---
title: ICommandImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl
- ICommandImpl::Cancel
- Cancel
- ICommandImpl.Cancel
- ICommandImpl::CancelExecution
- ATL::ICommandImpl::CancelExecution
- ATL.ICommandImpl.CancelExecution
- CancelExecution
- ICommandImpl.CancelExecution
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
- ICommandImpl::Execute
- ICommandImpl.Execute
- ICommandImpl::GetDBSession
- GetDBSession
- ICommandImpl.GetDBSession
- ATL.ICommandImpl.ICommandImpl
- ATL::ICommandImpl::ICommandImpl
- ICommandImpl
- ICommandImpl::ICommandImpl
- ICommandImpl.ICommandImpl
- ICommandImpl::m_bCancel
- ICommandImpl.m_bCancel
- m_bCancel
- ATL::ICommandImpl::m_bCancel
- ATL.ICommandImpl.m_bCancel
- ICommandImpl::m_bCancelWhenExecuting
- ICommandImpl.m_bCancelWhenExecuting
- ATL::ICommandImpl::m_bCancelWhenExecuting
- m_bCancelWhenExecuting
- ATL.ICommandImpl.m_bCancelWhenExecuting
- ICommandImpl.m_bIsExecuting
- ATL::ICommandImpl::m_bIsExecuting
- m_bIsExecuting
- ATL.ICommandImpl.m_bIsExecuting
- ICommandImpl::m_bIsExecuting
dev_langs:
- C++
helpviewer_keywords:
- ICommandImpl class
- Cancel method
- CancelExecution method
- CreateRowset method
- Execute method
- GetDBSession method
- ICommandImpl constructor
- ICommandImpl class, constructor
- m_bCancel
- m_bCancelWhenExecuting
- m_bIsExecuting
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 07453e3040594332857ba75455b1847a3914fdd2
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337795"
---
# <a name="icommandimpl-class"></a>ICommandImpl クラス
実装を提供、 [ICommand](https://msdn.microsoft.com/library/ms709737.aspx)インターフェイス。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class CommandBase = ICommand>   
class ATL_NO_VTABLE ICommandImpl : public CommandBase  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`ICommandImpl`します。  
  
 *CommandBase*  
 コマンド インターフェイスです。 既定値は `ICommand` です。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[キャンセル](#cancel)|現在のコマンドの実行をキャンセルします。|  
|[CancelExecution](#cancelexecution)|現在のコマンドの実行をキャンセルします。|  
|[CreateRowset](#createrowset)|行セット オブジェクトを作成します。|  
|[実行](#execute)|コマンドを実行します。|  
|[GetDBSession](#getdbsession)|コマンドを作成したセッションにインターフェイス ポインターを返します。|  
|[ICommandImpl](#icommandimpl)|コンストラクターです。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_bCancel](#bcancel)|コマンドが取り消されるかどうかを示します。|  
|[m_bCancelWhenExecuting](#bcancelwhenexecuting)|コマンドを実行中にキャンセルするかどうかを示します。|  
|[m_bIsExecuting](#bisexecuting)|コマンドが現在実行されているかどうかを示します。|  
  
## <a name="remarks"></a>Remarks  
 コマンド オブジェクトの必須インターフェイス。  
  
## <a name="cancel"></a> Icommandimpl::cancel
現在のコマンドの実行をキャンセルします。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(Cancel)();  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[icommand::cancel](https://msdn.microsoft.com/library/ms714402.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  

## <a name="cancelexecution"></a> Icommandimpl::cancelexecution
現在のコマンドの実行をキャンセルします。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT CancelExecution();  
```  

## <a name="createrowset"></a> Icommandimpl::createrowset
によって呼び出される[Execute](../../data/oledb/icommandimpl-execute.md)を 1 つの行セットを作成します。  
  
### <a name="syntax"></a>構文  
  
```cpp
template template <class RowsetClass>  
HRESULT CreateRowset(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *RowsetClass*  
 ユーザーの行セット クラスを表すテンプレート クラスのメンバー。 通常、ウィザードによって生成されます。  
  
 *pUnkOuter*  
 [in]制御側へのポインター`IUnknown`インターフェイスの行セットが集計の一部として作成される場合は、それ以外の場合は null です。  
  
 *riid*  
 [in]対応する*riid*で`ICommand::Execute`します。  
  
 *pParams*  
 [入力/出力]対応する*pParams*で`ICommand::Execute`します。  
  
 *入力/出力*  
 対応する*入力/出力*で`ICommand::Execute`します。  
  
 *ppRowset*  
 [入力/出力]対応する*ppRowset*で`ICommand::Execute`します。  
  
 *pRowsetObj*  
 [out]行セット オブジェクトへのポインター。 通常、このパラメーターは使用されませんが COM オブジェクトに渡す前に、行セットに対してより多くの作業を実行する必要がある場合に使用できます。 有効期間*pRowsetObj*連結された*ppRowset*します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。 参照してください`ICommand::Execute`の一般的な値の一覧についてはします。  
  
### <a name="remarks"></a>Remarks  
 1 つ以上の行セットを作成するか、別の行セットを作成するための独自の条件を提供するには、別の呼び出しを配置`CreateRowset`内から`Execute`します。  
  
 参照してください[icommand::execute](https://msdn.microsoft.com/library/ms718095.aspx)で、 *OLE DB プログラマーズ リファレンス。*  

## <a name="execute"></a> Icommandimpl::execute
コマンドを実行します。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT Execute(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[icommand::execute](https://msdn.microsoft.com/library/ms718095.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  
 要求された発信インターフェイスは、この関数を作成する、行セット オブジェクトから取得したインターフェイスになります。  
  
 `Execute` 呼び出し[CreateRowset](../../data/oledb/icommandimpl-createrowset.md)します。 1 つ以上の行セットを作成するか、別の行セットを作成するための独自の条件を提供する既定の実装をオーバーライドします。  

## <a name="getdbsession"></a> Icommandimpl::getdbsession
コマンドを作成したセッションにインターフェイス ポインターを返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (GetDBSession) (REFIID riid,  
   IUnknown** ppSession);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[ICommand::GetDBSession](https://msdn.microsoft.com/library/ms719622.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  
 セッションからプロパティを取得するために便利です。  

## <a name="icommandimpl"></a> Icommandimpl::icommandimpl
コンストラクターです。  
  
### <a name="syntax"></a>構文  
  
```cpp
ICommandImpl();  
```  

## <a name="bcancel"></a> Icommandimpl::m_bcancel
コマンドが取り消されたかどうかを示します。  
  
### <a name="syntax"></a>構文  
  
```cpp
unsigned m_bCancel:1;  
```  
  
### <a name="remarks"></a>Remarks  
 この変数を取得することができます、`Execute`コマンド クラスと適切なキャンセルのメソッド。 

## <a name="bcancelwhenexecuting"></a> Icommandimpl::m_bcancelwhenexecuting
実行時にコマンドをキャンセルできるかどうかを示します。  
  
### <a name="syntax"></a>構文  
  
```cpp
unsigned m_bCancelWhenExecuting:1;  
```  
  
### <a name="remarks"></a>Remarks  
 既定値は**true** (キャンセルできます)。  

## <a name="bisexecuting"></a> Icommandimpl::m_bisexecuting
コマンドが現在実行されているかどうかを示します。  
  
### <a name="syntax"></a>構文  
  
```cpp
unsigned m_bIsExecuting:1;  
```  
  
### <a name="remarks"></a>Remarks  
 `Execute`コマンド クラスのメソッドでは、この変数に設定**true**します。 
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
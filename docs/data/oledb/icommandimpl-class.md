---
title: ICommandImpl クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: b235a85ccab4fd3d3377e656b53276928b425d94
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232158"
---
# <a name="icommandimpl-class"></a>ICommandImpl クラス

[ICommand](/previous-versions/windows/desktop/ms709737(v=vs.85))インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <class T, class CommandBase = ICommand>
class ATL_NO_VTABLE ICommandImpl : public CommandBase
```

### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `ICommandImpl` 。

*CommandBase*<br/>
コマンドインターフェイス。 既定値は、`ICommand` です。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[キャンセル](#cancel)|現在のコマンドの実行をキャンセルします。|
|[CancelExecution](#cancelexecution)|現在のコマンドの実行をキャンセルします。|
|[CreateRowset](#createrowset)|行セットオブジェクトを作成します。|
|[おい](#execute)|コマンドを実行します。|
|[GetDBSession](#getdbsession)|コマンドを作成したセッションへのインターフェイスポインターを返します。|
|[ICommandImpl](#icommandimpl)|コンストラクターです。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[m_bCancel](#bcancel)|コマンドを取り消すかどうかを示します。|
|[m_bCancelWhenExecuting](#bcancelwhenexecuting)|実行時にコマンドをキャンセルするかどうかを示します。|
|[m_bIsExecuting](#bisexecuting)|コマンドが現在実行されているかどうかを示します。|

## <a name="remarks"></a>解説

Command オブジェクトの必須のインターフェイスです。

## <a name="icommandimplcancel"></a><a name="cancel"></a>ICommandImpl:: Cancel

現在のコマンドの実行をキャンセルします。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(Cancel)();
```

### <a name="remarks"></a>解説

*OLE DB プログラマーリファレンス*の「 [ICommand:: Cancel](/previous-versions/windows/desktop/ms714402(v=vs.85)) 」を参照してください。

## <a name="icommandimplcancelexecution"></a><a name="cancelexecution"></a>ICommandImpl:: CancelExecution

現在のコマンドの実行をキャンセルします。

### <a name="syntax"></a>構文

```cpp
HRESULT CancelExecution();
```

## <a name="icommandimplcreaterowset"></a><a name="createrowset"></a>ICommandImpl:: CreateRowset

1つの行セットを作成するために[Execute](../../data/oledb/icommandimpl-execute.md)によって呼び出されます。

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

*RowsetClass*<br/>
ユーザーの行セットクラスを表すテンプレートクラスメンバー。 通常、ウィザードによって生成されます。

*pUnkOuter*<br/>
から`IUnknown`行セットが集計の一部として作成されている場合は、制御インターフェイスへのポインター。それ以外の場合は null です。

*riid*<br/>
からの*riid*に対応 `ICommand::Execute` します。

*pParams*<br/>
[入力/出力]の*Pparams*に対応 `ICommand::Execute` します。

*pcRowsAffected*<br/>
の*pcRowsAffected*に対応 `ICommand::Execute` します。

*ppRowset*<br/>
[入力/出力]の*ppRowset*に対応 `ICommand::Execute` します。

*pRowsetObj*<br/>
入出力行セットオブジェクトへのポインター。 通常、このパラメーターは使用されませんが、COM オブジェクトに渡す前に行セットに対してより多くの作業を実行する必要がある場合に使用できます。 *PRowsetObj*の有効期間は*ppRowset*によって制限されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。 `ICommand::Execute`一般的な値の一覧については、「」を参照してください。

### <a name="remarks"></a>解説

複数の行セットを作成する場合、または異なる行セットを作成するための独自の条件を指定する場合は、内からへの異なる呼び出しを配置し `CreateRowset` `Execute` ます。

*OLE DB プログラマーリファレンス*の「 [ICommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) 」を参照してください。

## <a name="icommandimplexecute"></a><a name="execute"></a>ICommandImpl:: Execute

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

*OLE DB プログラマーリファレンス*の「 [ICommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

要求される送信インターフェイスは、この関数によって作成される行セットオブジェクトから取得されたインターフェイスになります。

`Execute`[CreateRowset](../../data/oledb/icommandimpl-createrowset.md)を呼び出します。 複数の行セットを作成したり、異なる行セットを作成するための独自の条件を指定したりするには、既定の実装をオーバーライドします。

## <a name="icommandimplgetdbsession"></a><a name="getdbsession"></a>ICommandImpl:: GetDBSession

コマンドを作成したセッションへのインターフェイスポインターを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetDBSession) (REFIID riid,
   IUnknown** ppSession);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [ICommand:: getdbsession](/previous-versions/windows/desktop/ms719622(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

セッションからプロパティを取得する場合に便利です。

## <a name="icommandimplicommandimpl"></a><a name="icommandimpl"></a>ICommandImpl:: ICommandImpl

コンストラクターです。

### <a name="syntax"></a>構文

```cpp
ICommandImpl();
```

## <a name="icommandimplm_bcancel"></a><a name="bcancel"></a>ICommandImpl:: m_bCancel

コマンドがキャンセルされたかどうかを示します。

### <a name="syntax"></a>構文

```cpp
unsigned m_bCancel:1;
```

### <a name="remarks"></a>解説

この変数は、 `Execute` command クラスのメソッドで取得し、必要に応じて取り消すことができます。

## <a name="icommandimplm_bcancelwhenexecuting"></a><a name="bcancelwhenexecuting"></a>ICommandImpl:: m_bCancelWhenExecuting

実行時にコマンドを取り消すことができるかどうかを示します。

### <a name="syntax"></a>構文

```cpp
unsigned m_bCancelWhenExecuting:1;
```

### <a name="remarks"></a>解説

既定値は **`true`** です (取り消すことができます)。

## <a name="icommandimplm_bisexecuting"></a><a name="bisexecuting"></a>ICommandImpl:: m_bIsExecuting

コマンドが現在実行されているかどうかを示します。

### <a name="syntax"></a>構文

```cpp
unsigned m_bIsExecuting:1;
```

### <a name="remarks"></a>解説

`Execute`Command クラスのメソッドは、この変数をに設定でき **`true`** ます。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)

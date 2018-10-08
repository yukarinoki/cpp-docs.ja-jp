---
title: AsyncBase クラス |Microsoft Docs
ms.custom: ''
ms.date: 10/08/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase
- async/Microsoft::WRL::AsyncBase::AsyncBase
- async/Microsoft::WRL::AsyncBase::Cancel
- async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall
- async/Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall
- async/Microsoft::WRL::AsyncBase::Close
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
- async/Microsoft::WRL::AsyncBase::CurrentStatus
- async/Microsoft::WRL::AsyncBase::ErrorCode
- async/Microsoft::WRL::AsyncBase::FireCompletion
- async/Microsoft::WRL::AsyncBase::FireProgress
- async/Microsoft::WRL::AsyncBase::get_ErrorCode
- async/Microsoft::WRL::AsyncBase::get_Id
- async/Microsoft::WRL::AsyncBase::get_Status
- async/Microsoft::WRL::AsyncBase::GetOnComplete
- async/Microsoft::WRL::AsyncBase::GetOnProgress
- async/Microsoft::WRL::AsyncBase::OnCancel
- async/Microsoft::WRL::AsyncBase::OnClose
- async/Microsoft::WRL::AsyncBase::OnStart
- async/Microsoft::WRL::AsyncBase::put_Id
- async/Microsoft::WRL::AsyncBase::PutOnComplete
- async/Microsoft::WRL::AsyncBase::PutOnProgress
- async/Microsoft::WRL::AsyncBase::Start
- async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::AsyncBase class
- Microsoft::WRL::AsyncBase::AsyncBase, constructor
- Microsoft::WRL::AsyncBase::Cancel method
- Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall method
- Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall method
- Microsoft::WRL::AsyncBase::Close method
- Microsoft::WRL::AsyncBase::ContinueAsyncOperation method
- Microsoft::WRL::AsyncBase::CurrentStatus method
- Microsoft::WRL::AsyncBase::ErrorCode method
- Microsoft::WRL::AsyncBase::FireCompletion method
- Microsoft::WRL::AsyncBase::FireProgress method
- Microsoft::WRL::AsyncBase::get_ErrorCode method
- Microsoft::WRL::AsyncBase::get_Id method
- Microsoft::WRL::AsyncBase::get_Status method
- Microsoft::WRL::AsyncBase::GetOnComplete method
- Microsoft::WRL::AsyncBase::GetOnProgress method
- Microsoft::WRL::AsyncBase::OnCancel method
- Microsoft::WRL::AsyncBase::OnClose method
- Microsoft::WRL::AsyncBase::OnStart method
- Microsoft::WRL::AsyncBase::put_Id method
- Microsoft::WRL::AsyncBase::PutOnComplete method
- Microsoft::WRL::AsyncBase::PutOnProgress method
- Microsoft::WRL::AsyncBase::Start method
- Microsoft::WRL::AsyncBase::TryTransitionToCompleted method
- Microsoft::WRL::AsyncBase::TryTransitionToError method
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a1003553cb0c3fc3abc8c24a6870485816397eaa
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861955"
---
# <a name="asyncbase-class"></a>AsyncBase クラス

Windows ランタイムの非同期ステート マシンを実装します。

## <a name="syntax"></a>構文

```cpp
template <
    typename TComplete,
    typename TProgress = Details::Nil,
    AsyncResultType resultType = SingleResult
>
class AsyncBase : public AsyncBase<TComplete, Details::Nil, resultType>;

template <typename TComplete, AsyncResultType resultType>
class AsyncBase<TComplete, Details::Nil, resultType> :
    public Microsoft::WRL::Implements<IAsyncInfo>;
```

### <a name="parameters"></a>パラメーター

*TComplete*<br/>
非同期操作の完了時に呼び出されるイベント ハンドラー。

*TProgress*<br/>
実行中の非同期操作が現在の操作の進行状況を報告したときに呼び出されるイベント ハンドラー。

*resultType*<br/>
1 つ、 [AsyncResultType](../windows/asyncresulttype-enumeration.md)列挙値。 既定では、`SingleResult`します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                               | 説明
---------------------------------- | -------------------------------------------------
[Asyncbase::asyncbase](#asyncbase) | `AsyncBase` クラスのインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                         | 説明
-------------------------------------------- | -------------------------------------------------------------------------------------
[Asyncbase::cancel](#cancel)                 | 非同期操作をキャンセルします。
[Asyncbase::close](#close)                   | 非同期操作を閉じます。
[Asyncbase::firecompletion](#firecompletion) | 完了イベント ハンドラーを呼び出します。 または内部の進行状況のデリゲートをリセットします。
[Asyncbase::fireprogress](#fireprogress)     | 現在の進行状況イベント ハンドラーを呼び出します。
[Asyncbase::get_errorcode](#get-errorcode)   | 現在の非同期操作のエラー コードを取得します。
[Asyncbase::get_id](#get-id)                 | 非同期操作のハンドルを取得します。
[Asyncbase::get_status](#get-status)         | 非同期操作の状態を示す値を取得します。
[Asyncbase::getoncomplete](#getoncomplete)   | 指定された変数には、現在の完了イベント ハンドラーのアドレスをコピーします。
[Asyncbase::getonprogress](#getonprogress)   | 指定された変数には、現在の進行状況イベント ハンドラーのアドレスをコピーします。
[Asyncbase::put_id](#put-id)                 | 非同期操作のハンドルを設定します。
[Asyncbase::putoncomplete](#putoncomplete)   | 完了イベントのハンドラーのアドレスを指定した値に設定します。
[Asyncbase::putonprogress](#putonprogress)   | 進行状況イベント ハンドラーのアドレスを指定した値に設定します。
[Asyncbase::start](#start)                   | 非同期操作を開始します。

### <a name="protected-methods"></a>プロテクト メソッド

名前                                                                         | 説明
---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[Asyncbase::checkvalidstatefordelegatecall](#checkvalidstatefordelegatecall) | 現在の非同期状態でデリゲート プロパティを変更できるかどうかをテストします。
[Asyncbase::checkvalidstateforresultscall](#checkvalidstateforresultscall)   | 現在の非同期状態に非同期操作の結果を収集できるかどうかをテストします。
[Asyncbase::continueasyncoperation](#continueasyncoperation)                 | 非同期操作が処理を続行する必要がありますまたは中止するかどうかを判断します。
[Asyncbase::currentstatus](#currentstatus)                                   | 現在の非同期操作の状態を取得します。
[Asyncbase::errorcode](#errorcode)                                           | 現在の非同期操作のエラー コードを取得します。
[Asyncbase::oncancel](#oncancel)                                             | 派生クラスでオーバーライドされると、非同期操作をキャンセルします。
[Asyncbase::onclose](#onclose)                                               | 派生クラスでオーバーライドされると、非同期操作を終了します。
[Asyncbase::onstart](#onstart)                                               | 派生クラスでオーバーライドされると、非同期操作を開始します。
[Asyncbase::trytransitiontocompleted](#trytransitiontocompleted)             | 現在の非同期操作が完了したかどうかを示します。
[Asyncbase::trytransitiontoerror](#trytransitiontoerror)                     | 指定したエラー コードが内部エラー状態を変更できるかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL

## <a name="asyncbase"></a>Asyncbase::asyncbase

`AsyncBase` クラスのインスタンスを初期化します。

```cpp
AsyncBase();
```

## <a name="cancel"></a>Asyncbase::cancel

非同期操作をキャンセルします。

```cpp
STDMETHOD(
   Cancel
)(void);
```

### <a name="return-value"></a>戻り値

既定では、常に S_OK を返します。

### <a name="remarks"></a>Remarks

`Cancel()` 既定の実装は、 `IAsyncInfo::Cancel`、実際の作業を行いません。 実際には、非同期操作をキャンセルするには、オーバーライド、`OnCancel()`純粋仮想メソッド。

## <a name="checkvalidstatefordelegatecall"></a>Asyncbase::checkvalidstatefordelegatecall

現在の非同期状態でデリゲート プロパティを変更できるかどうかをテストします。

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

### <a name="return-value"></a>戻り値

デリゲートのプロパティを変更できる場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALL します。

## <a name="checkvalidstateforresultscall"></a>Asyncbase::checkvalidstateforresultscall

現在の非同期状態に非同期操作の結果を収集できるかどうかをテストします。

```cpp
inline HRESULT CheckValidStateForResultsCall();
```

### <a name="return-value"></a>戻り値

結果を収集する場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL します。

## <a name="close"></a>Asyncbase::close

非同期操作を閉じます。

```cpp
STDMETHOD(
   Close
)(void) override;
```

### <a name="return-value"></a>戻り値

操作を閉じるかまたは既に場合は S_OK が閉じられました。それ以外の場合、E_ILLEGAL_STATE_CHANGE します。

### <a name="remarks"></a>Remarks

`Close()` 既定の実装は、 `IAsyncInfo::Close`、実際の作業を行いません。 実際に閉じる非同期操作には、オーバーライド、`OnClose()`純粋仮想メソッド。

## <a name="continueasyncoperation"></a>Asyncbase::continueasyncoperation

非同期操作が処理を続行する必要がありますまたは中止するかどうかを判断します。

```cpp
inline bool ContinueAsyncOperation();
```

### <a name="return-value"></a>戻り値

`true` 非同期操作の現在の状態の場合*開始*、つまり、操作を続行する必要があります。 それ以外の場合、 `false`、つまり、操作を停止する必要があります。

## <a name="currentstatus"></a>Asyncbase::currentstatus

現在の非同期操作の状態を取得します。

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>パラメーター

*status*<br/>
この操作が現在の状態を格納する場所です。

### <a name="remarks"></a>Remarks

この操作は、スレッド セーフです。

## <a name="errorcode"></a>Asyncbase::errorcode

現在の非同期操作のエラー コードを取得します。

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>パラメーター

*error*<br/>
この操作が現在のエラー コードを格納する場所です。

### <a name="remarks"></a>Remarks

この操作は、スレッド セーフです。

## <a name="firecompletion"></a>Asyncbase::firecompletion

完了イベント ハンドラーを呼び出します。 または内部の進行状況のデリゲートをリセットします。

```cpp
void FireCompletion(
   void
) override;

virtual void FireCompletion();
```

### <a name="remarks"></a>Remarks

最初のバージョンの`FireCompletion()`内部の進行状況のデリゲート変数をリセットします。 2 番目のバージョンは、非同期操作が完了した場合、完了イベント ハンドラーを呼び出します。

## <a name="fireprogress"></a>Asyncbase::fireprogress

現在の進行状況イベント ハンドラーを呼び出します。

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>パラメーター

*arg*<br/>
呼び出すイベント ハンドラー メソッド。

### <a name="remarks"></a>Remarks

`ProgressTraits` 派生[ArgTraitsHelper 構造体](../windows/argtraitshelper-structure.md)します。

## <a name="get-errorcode"></a>Asyncbase::get_errorcode

現在の非同期操作のエラー コードを取得します。

```cpp
STDMETHOD(
   get_ErrorCode
)(HRESULT* errorCode) override;
```

### <a name="parameters"></a>パラメーター

*エラー コード*<br/>
現在のエラー コードが格納されている場所です。

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALL、現在の非同期操作が閉じている場合。

## <a name="get-id"></a>Asyncbase::get_id

非同期操作のハンドルを取得します。

```cpp
STDMETHOD(
   get_Id
)(unsigned int *id) override;
```

### <a name="parameters"></a>パラメーター

*ID*<br/>
ハンドルが格納される場所です。

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALL します。

### <a name="remarks"></a>Remarks

このメソッドは、`IAsyncInfo::get_Id` を実装します。

## <a name="get-status"></a>Asyncbase::get_status

非同期操作の状態を示す値を取得します。

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>パラメーター

*status*<br/>
状態が格納される場所です。 詳細については、次を参照してください。`Windows::Foundation::AsyncStatus`列挙体。

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALL します。

### <a name="remarks"></a>Remarks

このメソッドは、`IAsyncInfo::get_Status` を実装します。

## <a name="getoncomplete"></a>Asyncbase::getoncomplete

指定された変数には、現在の完了イベント ハンドラーのアドレスをコピーします。

```cpp
STDMETHOD(
   GetOnComplete
)(TComplete** completeHandler);
```

### <a name="parameters"></a>パラメーター

*completeHandler*<br/>
現在の完了イベント ハンドラーのアドレスが格納されている場所です。

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALL します。

## <a name="getonprogress"></a>Asyncbase::getonprogress

指定された変数には、現在の進行状況イベント ハンドラーのアドレスをコピーします。

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>パラメーター

*progressHandler*<br/>
現在の進行状況イベント ハンドラーのアドレスが格納されている場所です。

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALL します。

## <a name="oncancel"></a>Asyncbase::oncancel

派生クラスでオーバーライドされると、非同期操作をキャンセルします。

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="onclose"></a>Asyncbase::onclose

派生クラスでオーバーライドされると、非同期操作を終了します。

```cpp
virtual void OnClose(
   void
) = 0;
```

## <a name="onstart"></a>Asyncbase::onstart

派生クラスでオーバーライドされると、非同期操作を開始します。

```cpp
virtual HRESULT OnStart(
   void
) = 0;
```

## <a name="put-id"></a>Asyncbase::put_id

非同期操作のハンドルを設定します。

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>パラメーター

*ID*<br/>
0 以外のハンドル。

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_INVALIDARG または E_ILLEGAL_METHOD_CALL します。

## <a name="putoncomplete"></a>Asyncbase::putoncomplete

完了イベントのハンドラーのアドレスを指定した値に設定します。

```cpp
STDMETHOD(
   PutOnComplete
)(TComplete* completeHandler);
```

### <a name="parameters"></a>パラメーター

*completeHandler*<br/>
完了イベントのハンドラーが設定されているアドレスです。

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALL します。

## <a name="putonprogress"></a>Asyncbase::putonprogress

進行状況イベント ハンドラーのアドレスを指定した値に設定します。

```cpp
STDMETHOD(
   PutOnProgress
)(TProgress* progressHandler);
```

### <a name="parameters"></a>パラメーター

*progressHandler*<br/>
進行状況イベントのハンドラーが設定されているアドレスです。

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALL します。

## <a name="start"></a>Asyncbase::start

非同期操作を開始します。

```cpp
STDMETHOD(
   Start
)(void);
```

### <a name="return-value"></a>戻り値

S_OK 場合は、操作の開始またはが既に開始します。それ以外の場合、E_ILLEGAL_STATE_CHANGE します。

### <a name="remarks"></a>Remarks

`Start()` 既定の実装は、 `IAsyncInfo::Start`、実際の作業を行いません。 実際には、非同期操作を開始するには、オーバーライド、`OnStart()`純粋仮想メソッド。

## <a name="trytransitiontocompleted"></a>Asyncbase::trytransitiontocompleted

現在の非同期操作が完了したかどうかを示します。

```cpp
bool TryTransitionToCompleted(
   void
);
```

### <a name="return-value"></a>戻り値

`true` 非同期操作が完了している場合それ以外の場合、`false`します。

## <a name="trytransitiontoerror"></a>Asyncbase::trytransitiontoerror

指定したエラー コードが内部エラー状態を変更できるかどうかを示します。

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>パラメーター

*error*<br/>
エラーの hresult 値。

### <a name="return-value"></a>戻り値

`true` 内部エラー状態が変更された場合それ以外の場合、`false`します。

### <a name="remarks"></a>Remarks

この操作は、エラー状態は S_OK を既に設定されている場合にのみ、エラー状態を変更します。 エラー状態であるエラー、キャンセル、完了すると、または閉じられた場合は、この操作を指定しても効果はありません。

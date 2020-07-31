---
title: AsyncBase クラス
ms.date: 10/08/2018
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
- async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
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
- Microsoft::WRL::AsyncBase::TryTransitionToCompleted method
- Microsoft::WRL::AsyncBase::TryTransitionToError method
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
ms.openlocfilehash: 8684096e76c08456a9c6813b7f04d79b820e41e5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211555"
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
非同期操作の完了時に呼び出されるイベントハンドラー。

*TProgress*<br/>
非同期操作の実行時に、操作の現在の進行状況を報告するときに呼び出されるイベントハンドラー。

*resultType*<br/>
[AsyncResultType](asyncresulttype-enumeration.md)列挙値のいずれか。 既定では、`SingleResult` になります。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                               | 説明
---------------------------------- | -------------------------------------------------
[AsyncBase:: AsyncBase](#asyncbase) | `AsyncBase` クラスのインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                         | 説明
-------------------------------------------- | -------------------------------------------------------------------------------------
[AsyncBase:: Cancel](#cancel)                 | 非同期操作をキャンセルします。
[AsyncBase:: Close](#close)                   | 非同期操作を終了します。
[AsyncBase:: 焼討 Completion](#firecompletion) | 完了イベントハンドラーを呼び出すか、内部進行状況デリゲートをリセットします。
[AsyncBase:: 焼討 Progress](#fireprogress)     | 現在の進行状況イベントハンドラーを呼び出します。
[AsyncBase:: get_ErrorCode](#get-errorcode)   | 現在の非同期操作のエラーコードを取得します。
[AsyncBase:: get_Id](#get-id)                 | 非同期操作のハンドルを取得します。
[AsyncBase:: get_Status](#get-status)         | 非同期操作の状態を示す値を取得します。
[AsyncBase:: GetOnComplete](#getoncomplete)   | 現在の完了イベントハンドラーのアドレスを、指定した変数にコピーします。
[AsyncBase:: GetOnProgress](#getonprogress)   | 現在の進行状況イベントハンドラーのアドレスを、指定した変数にコピーします。
[AsyncBase::p ut_Id](#put-id)                 | 非同期操作のハンドルを設定します。
[AsyncBase::P utOnComplete](#putoncomplete)   | 完了イベントハンドラーのアドレスを、指定した値に設定します。
[AsyncBase::P utOnProgress](#putonprogress)   | 進行状況イベントハンドラーのアドレスを、指定した値に設定します。

### <a name="protected-methods"></a>プロテクト メソッド

名前                                                                         | 説明
---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[AsyncBase:: CheckValidStateForDelegateCall](#checkvalidstatefordelegatecall) | 現在の非同期状態でデリゲートプロパティを変更できるかどうかをテストします。
[AsyncBase:: CheckValidStateForResultsCall](#checkvalidstateforresultscall)   | 非同期操作の結果を現在の非同期状態で収集できるかどうかをテストします。
[AsyncBase:: ContinueAsyncOperation](#continueasyncoperation)                 | 非同期操作を継続して処理するか、停止するかを決定します。
[AsyncBase:: CurrentStatus](#currentstatus)                                   | 現在の非同期操作の状態を取得します。
[AsyncBase:: ErrorCode](#errorcode)                                           | 現在の非同期操作のエラーコードを取得します。
[AsyncBase:: OnCancel](#oncancel)                                             | 派生クラスでオーバーライドされると、非同期操作をキャンセルします。
[AsyncBase:: OnClose](#onclose)                                               | 派生クラスでオーバーライドされると、非同期操作を終了します。
[AsyncBase:: OnStart](#onstart)                                               | 派生クラスでオーバーライドされると、非同期操作を開始します。
[AsyncBase:: Start](#start)                                                   | 非同期操作を開始します。
[AsyncBase:: Try遷移 Tiontocompleted](#trytransitiontocompleted)             | 現在の非同期操作が完了したかどうかを示します。
[AsyncBase:: Try遷移 Tiontoerror](#trytransitiontoerror)                     | 指定されたエラーコードが内部エラー状態を変更できるかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>必要条件

**ヘッダー:** async .h

**名前空間:** Microsoft::WRL

## <a name="asyncbaseasyncbase"></a><a name="asyncbase"></a>AsyncBase:: AsyncBase

`AsyncBase` クラスのインスタンスを初期化します。

```cpp
AsyncBase();
```

## <a name="asyncbasecancel"></a><a name="cancel"></a>AsyncBase:: Cancel

非同期操作をキャンセルします。

```cpp
STDMETHOD(
   Cancel
)(void);
```

### <a name="return-value"></a>戻り値

既定では、は常に S_OK を返します。

### <a name="remarks"></a>解説

`Cancel()`はの既定の実装で `IAsyncInfo::Cancel` あり、実際の処理は行われません。 実際に非同期操作をキャンセルするには、 `OnCancel()` 純粋仮想メソッドをオーバーライドします。

## <a name="asyncbasecheckvalidstatefordelegatecall"></a><a name="checkvalidstatefordelegatecall"></a>AsyncBase:: CheckValidStateForDelegateCall

現在の非同期状態でデリゲートプロパティを変更できるかどうかをテストします。

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

### <a name="return-value"></a>戻り値

デリゲートのプロパティを変更できるかどうかを S_OK します。それ以外の場合は、E_ILLEGAL_METHOD_CALL ます。

## <a name="asyncbasecheckvalidstateforresultscall"></a><a name="checkvalidstateforresultscall"></a>AsyncBase:: CheckValidStateForResultsCall

非同期操作の結果を現在の非同期状態で収集できるかどうかをテストします。

```cpp
inline HRESULT CheckValidStateForResultsCall();
```

### <a name="return-value"></a>戻り値

結果を収集できるかどうかを S_OK します。それ以外の場合は、E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL ます。

## <a name="asyncbaseclose"></a><a name="close"></a>AsyncBase:: Close

非同期操作を終了します。

```cpp
STDMETHOD(
   Close
)(void) override;
```

### <a name="return-value"></a>戻り値

操作が終了した場合、または既に閉じている場合は S_OK します。それ以外の場合は、E_ILLEGAL_STATE_CHANGE ます。

### <a name="remarks"></a>解説

`Close()`はの既定の実装で `IAsyncInfo::Close` あり、実際の処理は行われません。 非同期操作を実際に終了するには、 `OnClose()` 純粋仮想メソッドをオーバーライドします。

## <a name="asyncbasecontinueasyncoperation"></a><a name="continueasyncoperation"></a>AsyncBase:: ContinueAsyncOperation

非同期操作を継続して処理するか、停止するかを決定します。

```cpp
inline bool ContinueAsyncOperation();
```

### <a name="return-value"></a>戻り値

**`true`** 非同期操作の現在の状態が*開始*されている場合は。これは、操作を続行する必要があることを意味します。 それ以外の場合は、 **`false`** 操作が中断されることを意味します。

## <a name="asyncbasecurrentstatus"></a><a name="currentstatus"></a>AsyncBase:: CurrentStatus

現在の非同期操作の状態を取得します。

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>パラメーター

*status*<br/>
この操作で現在の状態が格納される場所。

### <a name="remarks"></a>解説

この操作はスレッドセーフです。

## <a name="asyncbaseerrorcode"></a><a name="errorcode"></a>AsyncBase:: ErrorCode

現在の非同期操作のエラーコードを取得します。

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>パラメーター

*error*<br/>
この操作で現在のエラーコードが格納される場所。

### <a name="remarks"></a>解説

この操作はスレッドセーフです。

## <a name="asyncbasefirecompletion"></a><a name="firecompletion"></a>AsyncBase:: 焼討 Completion

完了イベントハンドラーを呼び出すか、内部進行状況デリゲートをリセットします。

```cpp
void FireCompletion(
   void
) override;

virtual void FireCompletion();
```

### <a name="remarks"></a>解説

の最初のバージョンでは、 `FireCompletion()` 内部進行状況デリゲート変数がリセットされます。 2番目のバージョンは、非同期操作が完了した場合に完了イベントハンドラーを呼び出します。

## <a name="asyncbasefireprogress"></a><a name="fireprogress"></a>AsyncBase:: 焼討 Progress

現在の進行状況イベントハンドラーを呼び出します。

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>パラメーター

*arg*<br/>
呼び出すイベントハンドラーメソッド。

### <a name="remarks"></a>解説

`ProgressTraits`は[ArgTraitsHelper 構造体](argtraitshelper-structure.md)から派生します。

## <a name="asyncbaseget_errorcode"></a><a name="get-errorcode"></a>AsyncBase:: get_ErrorCode

現在の非同期操作のエラーコードを取得します。

```cpp
STDMETHOD(
   get_ErrorCode
)(HRESULT* errorCode) override;
```

### <a name="parameters"></a>パラメーター

*errorCode*<br/>
現在のエラーコードが格納されている場所。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、現在の非同期操作が終了している場合は E_ILLEGAL_METHOD_CALL します。

## <a name="asyncbaseget_id"></a><a name="get-id"></a>AsyncBase:: get_Id

非同期操作のハンドルを取得します。

```cpp
STDMETHOD(
   get_Id
)(unsigned int *id) override;
```

### <a name="parameters"></a>パラメーター

*id*<br/>
ハンドルが格納される場所。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL ます。

### <a name="remarks"></a>解説

このメソッドは、`IAsyncInfo::get_Id` を実装します。

## <a name="asyncbaseget_status"></a><a name="get-status"></a>AsyncBase:: get_Status

非同期操作の状態を示す値を取得します。

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>パラメーター

*status*<br/>
状態が格納される場所。 詳細については、「列挙型」を参照してください `Windows::Foundation::AsyncStatus` 。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL ます。

### <a name="remarks"></a>解説

このメソッドは、`IAsyncInfo::get_Status` を実装します。

## <a name="asyncbasegetoncomplete"></a><a name="getoncomplete"></a>AsyncBase:: GetOnComplete

現在の完了イベントハンドラーのアドレスを、指定した変数にコピーします。

```cpp
STDMETHOD(
   GetOnComplete
)(TComplete** completeHandler);
```

### <a name="parameters"></a>パラメーター

*completeHandler*<br/>
現在の完了イベントハンドラーのアドレスが格納される場所。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL ます。

## <a name="asyncbasegetonprogress"></a><a name="getonprogress"></a>AsyncBase:: GetOnProgress

現在の進行状況イベントハンドラーのアドレスを、指定した変数にコピーします。

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>パラメーター

*進行中のプラットフォーム*<br/>
現在の進行状況イベントハンドラーのアドレスが格納される場所。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL ます。

## <a name="asyncbaseoncancel"></a><a name="oncancel"></a>AsyncBase:: OnCancel

派生クラスでオーバーライドされると、非同期操作をキャンセルします。

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="asyncbaseonclose"></a><a name="onclose"></a>AsyncBase:: OnClose

派生クラスでオーバーライドされると、非同期操作を終了します。

```cpp
virtual void OnClose(
   void
) = 0;
```

## <a name="asyncbaseonstart"></a><a name="onstart"></a>AsyncBase:: OnStart

派生クラスでオーバーライドされると、非同期操作を開始します。

```cpp
virtual HRESULT OnStart(
   void
) = 0;
```

## <a name="asyncbaseput_id"></a><a name="put-id"></a>AsyncBase::p ut_Id

非同期操作のハンドルを設定します。

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>パラメーター

*id*<br/>
0以外のハンドル。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、E_INVALIDARG または E_ILLEGAL_METHOD_CALL ます。

## <a name="asyncbaseputoncomplete"></a><a name="putoncomplete"></a>AsyncBase::P utOnComplete

完了イベントハンドラーのアドレスを、指定した値に設定します。

```cpp
STDMETHOD(
   PutOnComplete
)(TComplete* completeHandler);
```

### <a name="parameters"></a>パラメーター

*completeHandler*<br/>
完了イベントハンドラーの設定先のアドレス。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL ます。

## <a name="asyncbaseputonprogress"></a><a name="putonprogress"></a>AsyncBase::P utOnProgress

進行状況イベントハンドラーのアドレスを、指定した値に設定します。

```cpp
STDMETHOD(
   PutOnProgress
)(TProgress* progressHandler);
```

### <a name="parameters"></a>パラメーター

*進行中のプラットフォーム*<br/>
進行状況イベントハンドラーの設定先のアドレス。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL ます。

## <a name="asyncbasestart"></a><a name="start"></a>AsyncBase:: Start

非同期操作を開始します。

```cpp
STDMETHOD(
   Start
)(void);
```

### <a name="return-value"></a>戻り値

操作が開始された場合、または既に開始されている場合は S_OK します。それ以外の場合は、E_ILLEGAL_STATE_CHANGE ます。

### <a name="remarks"></a>解説

`Start()`は、非同期操作 "ホットスタート" が呼び出し元に戻る前に、外部から参照できない保護されたメソッドです。

## <a name="asyncbasetrytransitiontocompleted"></a><a name="trytransitiontocompleted"></a>AsyncBase:: Try遷移 Tiontocompleted

現在の非同期操作が完了したかどうかを示します。

```cpp
bool TryTransitionToCompleted(
   void
);
```

### <a name="return-value"></a>戻り値

**`true`** 非同期操作が完了した場合は。それ以外の場合は **`false`** 。

## <a name="asyncbasetrytransitiontoerror"></a><a name="trytransitiontoerror"></a>AsyncBase:: Try遷移 Tiontoerror

指定されたエラーコードが内部エラー状態を変更できるかどうかを示します。

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>パラメーター

*error*<br/>
エラー HRESULT。

### <a name="return-value"></a>戻り値

**`true`** 内部エラー状態が変更された場合は。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

この操作では、エラー状態が既に S_OK に設定されている場合にのみ、エラー状態が変更されます。 エラー状態が既にエラー、取り消し済み、完了、または終了の場合、この操作は無効です。

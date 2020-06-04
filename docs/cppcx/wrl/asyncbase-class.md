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
ms.openlocfilehash: 0254aa4dc243eeffa43850c437a833a6530c01e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371858"
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

*コンプリート*<br/>
非同期操作の完了時に呼び出されるイベント ハンドラー。

*プログレス*<br/>
実行中の非同期操作が現在の操作の進行状況を報告するときに呼び出されるイベント ハンドラー。

*resultType*<br/>
列挙値の 1[つ](asyncresulttype-enumeration.md)。 既定では、`SingleResult` になります。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                               | 説明
---------------------------------- | -------------------------------------------------
[非同期ベース::非同期ベース](#asyncbase) | `AsyncBase` クラスのインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                         | 説明
-------------------------------------------- | -------------------------------------------------------------------------------------
[非同期ベース::キャンセル](#cancel)                 | 非同期操作をキャンセルします。
[非同期ベース::閉じる](#close)                   | 非同期操作を閉じます。
[非同期ベース::火災完了](#firecompletion) | 完了イベント ハンドラーを呼び出すか、内部進捗デリゲートをリセットします。
[非同期ベース::火災プログレス](#fireprogress)     | 現在の進行状況イベント ハンドラーを呼び出します。
[非同期ベース::get_ErrorCode](#get-errorcode)   | 現在の非同期操作のエラー コードを取得します。
[非同期ベース::get_Id](#get-id)                 | 非同期操作のハンドルを取得します。
[非同期ベース::get_Status](#get-status)         | 非同期操作の状態を示す値を取得します。
[非同期ベース::ゲットオンコンプリート](#getoncomplete)   | 現在の完了イベント ハンドラーのアドレスを指定した変数にコピーします。
[非同期ベース::ゲットオンプログレス](#getonprogress)   | 現在の進行状況イベント ハンドラーのアドレスを、指定した変数にコピーします。
[非同期ベース::p](#put-id)                 | 非同期操作のハンドルを設定します。
[非同期ベース::Pコンプリート](#putoncomplete)   | 完了イベント ハンドラーのアドレスを指定した値に設定します。
[非同期ベース::P](#putonprogress)   | progress イベント ハンドラのアドレスを指定した値に設定します。

### <a name="protected-methods"></a>プロテクト メソッド

名前                                                                         | 説明
---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[非同期ベース::チェックValidステートフォーデリゲートコール](#checkvalidstatefordelegatecall) | 現在の非同期状態でデリゲート プロパティを変更できるかどうかをテストします。
[非同期ベース::チェックValidステートフォー結果呼び出し](#checkvalidstateforresultscall)   | 現在の非同期状態で非同期操作の結果を収集できるかどうかをテストします。
[非同期ベース::継続非同期操作](#continueasyncoperation)                 | 非同期操作の処理を続行するか、停止するかを決定します。
[非同期ベース::現在のステータス](#currentstatus)                                   | 現在の非同期操作の状態を取得します。
[非同期ベース::エラーコード](#errorcode)                                           | 現在の非同期操作のエラー コードを取得します。
[非同期ベース::オンキャンセル](#oncancel)                                             | 派生クラスでオーバーライドされると、非同期操作をキャンセルします。
[非同期ベース::オンクローズ](#onclose)                                               | 派生クラスでオーバーライドされると、非同期操作を閉じます。
[非同期ベース::オンスタート](#onstart)                                               | 派生クラスでオーバーライドされると、非同期操作を開始します。
[非同期ベース::開始](#start)                                                   | 非同期操作を開始します。
[非同期ベース::完了しました](#trytransitiontocompleted)             | 現在の非同期操作が完了したかどうかを示します。
[非同期ベース::エラーを変換します。](#trytransitiontoerror)                     | 指定されたエラー コードが内部エラー状態を変更できるかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>必要条件

**ヘッダー:** 非同期.h

**名前空間:** Microsoft::WRL

## <a name="asyncbaseasyncbase"></a><a name="asyncbase"></a>非同期ベース::非同期ベース

`AsyncBase` クラスのインスタンスを初期化します。

```cpp
AsyncBase();
```

## <a name="asyncbasecancel"></a><a name="cancel"></a>非同期ベース::キャンセル

非同期操作をキャンセルします。

```cpp
STDMETHOD(
   Cancel
)(void);
```

### <a name="return-value"></a>戻り値

既定では、常にS_OKを返します。

### <a name="remarks"></a>解説

`Cancel()`は の既定の`IAsyncInfo::Cancel`実装であり、実際の作業は行いません。 非同期操作を実際にキャンセルするには、純粋`OnCancel()`仮想メソッドをオーバーライドします。

## <a name="asyncbasecheckvalidstatefordelegatecall"></a><a name="checkvalidstatefordelegatecall"></a>非同期ベース::チェックValidステートフォーデリゲートコール

現在の非同期状態でデリゲート プロパティを変更できるかどうかをテストします。

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

### <a name="return-value"></a>戻り値

デリゲートのプロパティを変更できる場合はS_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL。

## <a name="asyncbasecheckvalidstateforresultscall"></a><a name="checkvalidstateforresultscall"></a>非同期ベース::チェックValidステートフォー結果呼び出し

現在の非同期状態で非同期操作の結果を収集できるかどうかをテストします。

```cpp
inline HRESULT CheckValidStateForResultsCall();
```

### <a name="return-value"></a>戻り値

結果を収集できる場合はS_OKします。それ以外の場合は、E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL。

## <a name="asyncbaseclose"></a><a name="close"></a>非同期ベース::閉じる

非同期操作を閉じます。

```cpp
STDMETHOD(
   Close
)(void) override;
```

### <a name="return-value"></a>戻り値

操作が終了するか、既に閉じている場合はS_OK。それ以外の場合は、E_ILLEGAL_STATE_CHANGE。

### <a name="remarks"></a>解説

`Close()`は の既定の`IAsyncInfo::Close`実装であり、実際の作業は行いません。 実際に非同期操作を閉じるには、`OnClose()`純粋仮想メソッドをオーバーライドします。

## <a name="asyncbasecontinueasyncoperation"></a><a name="continueasyncoperation"></a>非同期ベース::継続非同期操作

非同期操作の処理を続行するか、停止するかを決定します。

```cpp
inline bool ContinueAsyncOperation();
```

### <a name="return-value"></a>戻り値

非同期操作の現在の状態が*開始*されている場合**は true。** それ以外の場合は**false**を指定すると、操作は停止します。

## <a name="asyncbasecurrentstatus"></a><a name="currentstatus"></a>非同期ベース::現在のステータス

現在の非同期操作の状態を取得します。

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>パラメーター

*status*<br/>
この操作が現在の状態を格納する場所。

### <a name="remarks"></a>解説

この操作はスレッド セーフです。

## <a name="asyncbaseerrorcode"></a><a name="errorcode"></a>非同期ベース::エラーコード

現在の非同期操作のエラー コードを取得します。

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>パラメーター

*エラー*<br/>
この操作が現在のエラー コードを格納する場所。

### <a name="remarks"></a>解説

この操作はスレッド セーフです。

## <a name="asyncbasefirecompletion"></a><a name="firecompletion"></a>非同期ベース::火災完了

完了イベント ハンドラーを呼び出すか、内部進捗デリゲートをリセットします。

```cpp
void FireCompletion(
   void
) override;

virtual void FireCompletion();
```

### <a name="remarks"></a>解説

の最初の`FireCompletion()`バージョンは、内部進捗状況デリゲート変数をリセットします。 2 番目のバージョンでは、非同期操作が完了した場合に完了イベント ハンドラーが呼び出されます。

## <a name="asyncbasefireprogress"></a><a name="fireprogress"></a>非同期ベース::火災プログレス

現在の進行状況イベント ハンドラーを呼び出します。

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>パラメーター

*Arg*<br/>
呼び出すイベント ハンドラー メソッド。

### <a name="remarks"></a>解説

`ProgressTraits`は[、ArgTraitsHelper 構造体](argtraitshelper-structure.md)から派生します。

## <a name="asyncbaseget_errorcode"></a><a name="get-errorcode"></a>非同期ベース::get_ErrorCode

現在の非同期操作のエラー コードを取得します。

```cpp
STDMETHOD(
   get_ErrorCode
)(HRESULT* errorCode) override;
```

### <a name="parameters"></a>パラメーター

*errorCode*<br/>
現在のエラー コードが格納されている場所。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、現在の非同期操作が閉じている場合E_ILLEGAL_METHOD_CALL。

## <a name="asyncbaseget_id"></a><a name="get-id"></a>非同期ベース::get_Id

非同期操作のハンドルを取得します。

```cpp
STDMETHOD(
   get_Id
)(unsigned int *id) override;
```

### <a name="parameters"></a>パラメーター

*id*<br/>
ハンドルを格納する場所。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL。

### <a name="remarks"></a>解説

このメソッドは、`IAsyncInfo::get_Id` を実装します。

## <a name="asyncbaseget_status"></a><a name="get-status"></a>非同期ベース::get_Status

非同期操作の状態を示す値を取得します。

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>パラメーター

*status*<br/>
ステータスを格納する場所。 詳細については、「列挙」`Windows::Foundation::AsyncStatus`を参照してください。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL。

### <a name="remarks"></a>解説

このメソッドは、`IAsyncInfo::get_Status` を実装します。

## <a name="asyncbasegetoncomplete"></a><a name="getoncomplete"></a>非同期ベース::ゲットオンコンプリート

現在の完了イベント ハンドラーのアドレスを指定した変数にコピーします。

```cpp
STDMETHOD(
   GetOnComplete
)(TComplete** completeHandler);
```

### <a name="parameters"></a>パラメーター

*完全ハンドラー*<br/>
現在の完了イベント ハンドラーのアドレスが格納されている場所。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL。

## <a name="asyncbasegetonprogress"></a><a name="getonprogress"></a>非同期ベース::ゲットオンプログレス

現在の進行状況イベント ハンドラーのアドレスを、指定した変数にコピーします。

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>パラメーター

*プログレスハンドラー*<br/>
現在の進行状況イベント ハンドラーのアドレスが格納されている場所。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL。

## <a name="asyncbaseoncancel"></a><a name="oncancel"></a>非同期ベース::オンキャンセル

派生クラスでオーバーライドされると、非同期操作をキャンセルします。

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="asyncbaseonclose"></a><a name="onclose"></a>非同期ベース::オンクローズ

派生クラスでオーバーライドされると、非同期操作を閉じます。

```cpp
virtual void OnClose(
   void
) = 0;
```

## <a name="asyncbaseonstart"></a><a name="onstart"></a>非同期ベース::オンスタート

派生クラスでオーバーライドされると、非同期操作を開始します。

```cpp
virtual HRESULT OnStart(
   void
) = 0;
```

## <a name="asyncbaseput_id"></a><a name="put-id"></a>非同期ベース::p

非同期操作のハンドルを設定します。

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>パラメーター

*id*<br/>
ゼロ以外のハンドル。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、E_INVALIDARGまたはE_ILLEGAL_METHOD_CALL。

## <a name="asyncbaseputoncomplete"></a><a name="putoncomplete"></a>非同期ベース::Pコンプリート

完了イベント ハンドラーのアドレスを指定した値に設定します。

```cpp
STDMETHOD(
   PutOnComplete
)(TComplete* completeHandler);
```

### <a name="parameters"></a>パラメーター

*完全ハンドラー*<br/>
完了イベント ハンドラーが設定されるアドレス。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL。

## <a name="asyncbaseputonprogress"></a><a name="putonprogress"></a>非同期ベース::P

progress イベント ハンドラのアドレスを指定した値に設定します。

```cpp
STDMETHOD(
   PutOnProgress
)(TProgress* progressHandler);
```

### <a name="parameters"></a>パラメーター

*プログレスハンドラー*<br/>
進行状況イベント ハンドラーが設定されるアドレス。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、E_ILLEGAL_METHOD_CALL。

## <a name="asyncbasestart"></a><a name="start"></a>非同期ベース::開始

非同期操作を開始します。

```cpp
STDMETHOD(
   Start
)(void);
```

### <a name="return-value"></a>戻り値

操作が開始されるか、既に開始されている場合はS_OK。それ以外の場合は、E_ILLEGAL_STATE_CHANGE。

### <a name="remarks"></a>解説

`Start()`は、非同期操作が呼び出し元に戻る前に "ホット スタート" であるため、外部から参照できない保護されたメソッドです。

## <a name="asyncbasetrytransitiontocompleted"></a><a name="trytransitiontocompleted"></a>非同期ベース::完了しました

現在の非同期操作が完了したかどうかを示します。

```cpp
bool TryTransitionToCompleted(
   void
);
```

### <a name="return-value"></a>戻り値

非同期操作が完了した場合は**true、** その他の操作は完了しました。それ以外の場合**は false。**

## <a name="asyncbasetrytransitiontoerror"></a><a name="trytransitiontoerror"></a>非同期ベース::エラーを変換します。

指定されたエラー コードが内部エラー状態を変更できるかどうかを示します。

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>パラメーター

*エラー*<br/>
エラー HRESULT。

### <a name="return-value"></a>戻り値

内部エラー状態が変更された場合は**true。** それ以外の場合**は false。**

### <a name="remarks"></a>解説

この操作は、エラー状態が既にS_OKに設定されている場合にのみ、エラー状態を変更します。 エラー状態が既にエラー、キャンセル、完了、またはクローズされている場合、この操作は無効です。

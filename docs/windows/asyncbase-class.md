---
title: AsyncBase クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase
dev_langs:
- C++
helpviewer_keywords:
- AsyncBase class
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 087ecf151b17c7c505b4b70d01913a44e113ad29
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428682"
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

template <
   typename TComplete,
   AsyncResultType resultType
>
class AsyncBase<TComplete, Details::Nil, resultType> : public Microsoft::WRL::Implements<IAsyncInfo>;
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

|名前|説明|
|----------|-----------------|
|[AsyncBase::AsyncBase コンストラクター](../windows/asyncbase-asyncbase-constructor.md)|インスタンスを初期化します、 **AsyncBase**クラス。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[AsyncBase::Cancel メソッド](../windows/asyncbase-cancel-method.md)|非同期操作をキャンセルします。|
|[AsyncBase::Close メソッド](../windows/asyncbase-close-method.md)|非同期操作を閉じます。|
|[AsyncBase::FireCompletion メソッド](../windows/asyncbase-firecompletion-method.md)|完了イベント ハンドラーを呼び出します。 または内部の進行状況のデリゲートをリセットします。|
|[AsyncBase::FireProgress メソッド](../windows/asyncbase-fireprogress-method.md)|現在の進行状況イベント ハンドラーを呼び出します。|
|[AsyncBase::get_ErrorCode メソッド](../windows/asyncbase-get-errorcode-method.md)|現在の非同期操作のエラー コードを取得します。|
|[AsyncBase::get_Id メソッド](../windows/asyncbase-get-id-method.md)|非同期操作のハンドルを取得します。|
|[AsyncBase::get_Status メソッド](../windows/asyncbase-get-status-method.md)|非同期操作の状態を示す値を取得します。|
|[AsyncBase::GetOnComplete メソッド](../windows/asyncbase-getoncomplete-method.md)|指定された変数には、現在の完了イベント ハンドラーのアドレスをコピーします。|
|[AsyncBase::GetOnProgress メソッド](../windows/asyncbase-getonprogress-method.md)|指定された変数には、現在の進行状況イベント ハンドラーのアドレスをコピーします。|
|[AsyncBase::put_Id メソッド](../windows/asyncbase-put-id-method.md)|非同期操作のハンドルを設定します。|
|[AsyncBase::PutOnComplete メソッド](../windows/asyncbase-putoncomplete-method.md)|完了イベントのハンドラーのアドレスを指定した値に設定します。|
|[AsyncBase::PutOnProgress メソッド](../windows/asyncbase-putonprogress-method.md)|進行状況イベント ハンドラーのアドレスを指定した値に設定します。|
|[AsyncBase::Start メソッド](../windows/asyncbase-start-method.md)|非同期操作を開始します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[AsyncBase::CheckValidStateForDelegateCall メソッド](../windows/asyncbase-checkvalidstatefordelegatecall-method.md)|現在の非同期状態でデリゲート プロパティを変更できるかどうかをテストします。|
|[AsyncBase::CheckValidStateForResultsCall メソッド](../windows/asyncbase-checkvalidstateforresultscall-method.md)|現在の非同期状態に非同期操作の結果を収集できるかどうかをテストします。|
|[AsyncBase::ContinueAsyncOperation メソッド](../windows/asyncbase-continueasyncoperation-method.md)|非同期操作が処理を続行する必要がありますまたは中止するかどうかを判断します。|
|[AsyncBase::CurrentStatus メソッド](../windows/asyncbase-currentstatus-method.md)|現在の非同期操作の状態を取得します。|
|[AsyncBase::ErrorCode メソッド](../windows/asyncbase-errorcode-method.md)|現在の非同期操作のエラー コードを取得します。|
|[AsyncBase::OnCancel メソッド](../windows/asyncbase-oncancel-method.md)|派生クラスでオーバーライドされると、非同期操作をキャンセルします。|
|[AsyncBase::OnClose メソッド](../windows/asyncbase-onclose-method.md)|派生クラスでオーバーライドされると、非同期操作を終了します。|
|[AsyncBase::OnStart メソッド](../windows/asyncbase-onstart-method.md)|派生クラスでオーバーライドされると、非同期操作を開始します。|
|[AsyncBase::TryTransitionToCompleted メソッド](../windows/asyncbase-trytransitiontocompleted-method.md)|現在の非同期操作が完了したかどうかを示します。|
|[AsyncBase::TryTransitionToError メソッド](../windows/asyncbase-trytransitiontoerror-method.md)|指定したエラー コードが内部エラー状態を変更できるかどうかを示します。|

## <a name="inheritance-hierarchy"></a>継承階層

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)
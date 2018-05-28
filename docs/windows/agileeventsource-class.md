---
title: AgileEventSource クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
- event/Microsoft::WRL::InvokeModeOptions
dev_langs:
- C++
helpviewer_keywords:
- AgileEventSource class
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 58eb96e3a0268d3ba70b60d9c315e935e19485f3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="agileeventsource-class"></a>AgileEventSource クラス

任意のスレッドからアクセス可能なコンポーネントは、アジャイル コンポーネントによって発生するイベントを表します。 継承[EventSource](eventsource-class.md)し、上書き、`Add`アジャイルのイベントを起動する方法のオプションを指定する追加の型パラメーターを持つメンバー関数。

## <a name="syntax"></a>構文

```
template<typename TDelegateInterface, typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>>
class AgileEventSource
    : public Microsoft::WRL::EventSource<TDelegateInterface, TEventSourceOptions>;
```

## <a name="parameters"></a>パラメーター  
 `TDelegateInterface`  

 デリゲートをイベント ハンドラーを表すインターフェイス。

 `TEventSourceOptions`  
 [InvokeModeOptions](invokemodeoptions-structure.md) invokeMode フィールドに設定されている構造`InvokeMode::StopOnFirstError`または`InvokeMode::FireAll`です。

## <a name="remarks"></a>コメント

Windows ランタイム コンポーネントの大部分は、アジャイル コンポーネントです。 詳細については、次を参照してください。[スレッドとマーシャ リング (C + + CX)](../cppcx/threading-and-marshaling-c-cx.md)です。

## <a name="inheritance-hierarchy"></a>継承階層

 `EventSource` `AgileEventSource`

## <a name="requirements"></a>要件

 **ヘッダー:** event.h

 **名前空間:** Microsoft::WRL

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[AgileEventSource::Add メソッド](#add)|現在の AgileEventSource オブジェクトのイベント ハンドラーのセットを指定したデリゲート インターフェイスによって表される、アジャイルのイベント ハンドラーを追加します。|

## <a name="add"></a> AgileEventSource::Add メソッド

現在のイベント ハンドラーのセットを指定したデリゲート インターフェイスによって表されるイベント ハンドラーを追加[EventSource](eventsource-class.md)オブジェクト。

### <a name="syntax"></a>構文

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>パラメーター

*delegateInterface*

インターフェイス、デリゲート オブジェクト、イベント ハンドラーを表します。

*トークン*この操作の完了時、イベントを表すハンドル。 Remove() メソッドにパラメーターとしてこのトークンを使用して、イベント ハンドラーを破棄します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。


## <a name="see-also"></a>関連項目

 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)

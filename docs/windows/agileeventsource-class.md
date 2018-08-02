---
title: AgileEventSource クラス |Microsoft Docs
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
ms.openlocfilehash: 7412968069963679db769cc2ce68169e7a8799b9
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462070"
---
# <a name="agileeventsource-class"></a>AgileEventSource クラス

任意のスレッドからアクセス可能なコンポーネントである、アジャイル コンポーネントによって発生するイベントを表します。 継承[EventSource](eventsource-class.md)をオーバーライドし、`Add`アジャイルのイベントを起動する方法のオプションを指定する追加の型パラメーターを持つメンバー関数。

## <a name="syntax"></a>構文

```
template<typename TDelegateInterface, typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>>
class AgileEventSource
    : public Microsoft::WRL::EventSource<TDelegateInterface, TEventSourceOptions>;
```

## <a name="parameters"></a>パラメーター  
 *TDelegateInterface*  

 イベント ハンドラーを表すデリゲートのインターフェイスです。

 *TEventSourceOptions*  
 [InvokeModeOptions](invokemodeoptions-structure.md) invokeMode フィールドに設定されている構造`InvokeMode::StopOnFirstError`または`InvokeMode::FireAll`します。

## <a name="remarks"></a>Remarks

Windows ランタイム コンポーネントの大半は、アジャイル コンポーネントです。 詳細については、次を参照してください。[スレッドとマーシャ リング (C + + CX)](../cppcx/threading-and-marshaling-c-cx.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

 `EventSource` `AgileEventSource`

## <a name="requirements"></a>要件

 **ヘッダー:** event.h

 **名前空間:** Microsoft::WRL

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[AgileEventSource::Add メソッド](#add)|現在の AgileEventSource オブジェクトのイベント ハンドラーのセットを指定したデリゲートをインターフェイスによって表されるアジャイル イベント ハンドラーを追加します。|

## <a name="add"></a> AgileEventSource::Add メソッド

現在のイベント ハンドラーのセットを指定したデリゲート インターフェイスによって表されるイベント ハンドラーを追加します。 [EventSource](eventsource-class.md)オブジェクト。

### <a name="syntax"></a>構文

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>パラメーター

*delegateInterface*  
イベント ハンドラーを表すデリゲート オブジェクトのインターフェイスです。

*token*  
この操作の完了時、イベントを表すハンドルです。 Remove() メソッドにパラメーターとしてこのトークンを使用して、イベント ハンドラーを破棄します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。


## <a name="see-also"></a>関連項目
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)
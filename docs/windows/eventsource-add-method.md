---
title: Eventsource::add メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Add
dev_langs:
- C++
helpviewer_keywords:
- Add method
ms.assetid: 8bded85b-929e-4425-a464-e5de67bb774c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a13c5b48a7e242f47903fda038331fd126832dcf
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592232"
---
# <a name="eventsourceadd-method"></a>EventSource::Add メソッド

現在のイベント ハンドラーのセットを指定したデリゲート インターフェイスによって表されるイベント ハンドラーを追加します。 **EventSource**オブジェクト。

## <a name="syntax"></a>構文

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
この操作の完了時、イベントを表すハンドルです。 パラメーターとしてこのトークンを使用して、 [Remove()](../windows/eventsource-remove-method.md)メソッドをイベント ハンドラーを破棄します。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目
[EventSource クラス](../windows/eventsource-class.md)
---
title: Eventsource::remove メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Remove
dev_langs:
- C++
helpviewer_keywords:
- Remove method
ms.assetid: afafedf5-3665-4408-a639-fb6884f7c5f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 00f3275095648a41eb25d10bac1f34637b2ac242
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604573"
---
# <a name="eventsourceremove-method"></a>EventSource::Remove メソッド

現在関連付けられているイベント ハンドラーのセットから、指定されたイベント登録トークンによって表されるイベント ハンドラーを削除します。 **EventSource**オブジェクト。

## <a name="syntax"></a>構文

```cpp
HRESULT Remove(
   EventRegistrationToken token
);
```

### <a name="parameters"></a>パラメーター

*token*  
イベント ハンドラーを表すハンドル。 このトークンはイベント ハンドラーの登録時に返された、 [Add()](../windows/eventsource-add-method.md)メソッド。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>Remarks

詳細については、`EventRegistrationToken`構造体を参照してください、 **Windows::Foundation::EventRegistrationToken 構造**でトピック、 **Windows ランタイム**リファレンス ドキュメント。

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目
[EventSource クラス](../windows/eventsource-class.md)
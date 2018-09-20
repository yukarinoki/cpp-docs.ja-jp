---
title: Handlet::handlet コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT, constructor
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d84bde2a9c83dedf6fa509101dddff85bd27999
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426121"
---
# <a name="handlethandlet-constructor"></a>HandleT::HandleT コンストラクター

新しいインスタンスを初期化、 **HandleT**クラス。

## <a name="syntax"></a>構文

```cpp
explicit HandleT(
   typename HandleTraits::Type h =
      HandleTraits::GetInvalidValue()  
);

HandleT(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
ハンドル。

## <a name="remarks"></a>Remarks

最初のコンス トラクターの初期化、 **HandleT**オブジェクトへの有効なハンドルではないオブジェクトです。 2 番目のコンス トラクターを作成、新しい**HandleT**パラメーターからオブジェクト*h*します。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HandleT クラス](../windows/handlet-class.md)
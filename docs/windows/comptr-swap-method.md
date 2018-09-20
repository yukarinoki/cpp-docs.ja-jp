---
title: Comptr::swap メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::Swap
dev_langs:
- C++
helpviewer_keywords:
- Swap method
ms.assetid: 74275f00-b24e-4b4c-b8b6-ac2aa2dd7ae9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ae79286adfd3885aba3e80344251c2d76ef63c61
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385470"
---
# <a name="comptrswap-method"></a>ComPtr::Swap メソッド

現在の管理インターフェイスを交換**ComPtr** 、指定した管理インターフェイスで**ComPtr**します。

## <a name="syntax"></a>構文

```cpp
void Swap(
   _Inout_ ComPtr&& r
);

void Swap(
   _Inout_ ComPtr& r
);
```

### <a name="parameters"></a>パラメーター

*r*<br/>
A **ComPtr**します。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[ComPtr クラス](../windows/comptr-class.md)
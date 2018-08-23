---
title: BoolStruct 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
dev_langs:
- C++
helpviewer_keywords:
- BoolStruct structure
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c4981c7f82fe2c544bf907ac59d6e9ca22105cbd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592538"
---
# <a name="boolstruct-structure"></a>BoolStruct 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>Remarks

**BoolStruct**構造体を定義するかどうかを`ComPtr`インターフェイスのオブジェクトの有効期間を管理します。 **BoolStruct**内部で使用される、 [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)演算子。

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[BoolStruct::Member データ メンバー](../windows/boolstruct-member-data-member.md)|指定します、 [ComPtr](../windows/comptr-class.md)またはインターフェイスのオブジェクトの有効期間の管理ではないです。|

## <a name="inheritance-hierarchy"></a>継承階層

`BoolStruct`

## <a name="requirements"></a>要件

**ヘッダー:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)  
[ComPtr::operator Microsoft::WRL::Details::BoolType 演算子](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)
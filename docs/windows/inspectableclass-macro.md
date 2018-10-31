---
title: InspectableClass マクロ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
dev_langs:
- C++
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 44bdcbc84a1ed2d57b0c9a0ce9eca4feebb0b133
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059702"
---
# <a name="inspectableclass-macro"></a>InspectableClass マクロ

ランタイム クラス名と信頼レベルを設定します。

## <a name="syntax"></a>構文

```cpp
InspectableClass(
   runtimeClassName,
   trustLevel)
```

### <a name="parameters"></a>パラメーター

*runtimeClassName*<br/>
ランタイム クラス名のテキスト形式の完全な名前です。

*trustLevel*<br/>
1 つ、 [TrustLevel](https://msdn.microsoft.com/library/br224625.aspx)列挙値。

## <a name="remarks"></a>Remarks

**InspectableClass**マクロは、Windows ランタイム型でのみ使用できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[RuntimeClass クラス](../windows/runtimeclass-class.md)
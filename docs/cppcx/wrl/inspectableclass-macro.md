---
title: InspectableClass マクロ
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: 9d194f5a87ac4a142301bc896cb3ed172f119473
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025712"
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
1 つ、 [TrustLevel](/windows/desktop/api/inspectable/ne-inspectable-trustlevel)列挙値。

## <a name="remarks"></a>Remarks

**InspectableClass**マクロは、Windows ランタイム型でのみ使用できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** implements.h

**名前空間:** Microsoft::wrl

## <a name="see-also"></a>関連項目

[RuntimeClass クラス](runtimeclass-class.md)
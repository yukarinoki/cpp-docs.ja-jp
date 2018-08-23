---
title: Hstring::hstring コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs:
- C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80af8f463d6cd1af631c6cb37c0239e7a9e85c3f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595886"
---
# <a name="hstringhstring-constructor"></a>HString::HString コンストラクター

新しいインスタンスを初期化、 **HString**クラス。

## <a name="syntax"></a>構文

```cpp
HString(HSTRING hstr = nullptr) throw();
HString(HString&& other) throw();
```

#### <a name="parameters"></a>パラメーター

*hstr*  
HSTRING ハンドルの場合。

*other*  
既存の**HString**オブジェクト。

## <a name="remarks"></a>Remarks

最初のコンス トラクターによって初期化新しい**HString**オブジェクトが空です。

2 番目のコンス トラクターによって初期化、新しい**HString**オブジェクト、既存の値から*他*パラメーター、し、その後破棄、*他*パラメーター。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HString クラス](../windows/hstring-class.md)
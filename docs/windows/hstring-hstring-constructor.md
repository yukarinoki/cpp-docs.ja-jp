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
ms.openlocfilehash: 59ec7c1635b825cc300e28e5c02e2a3864a6c123
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442254"
---
# <a name="hstringhstring-constructor"></a>HString::HString コンストラクター

新しいインスタンスを初期化、 **HString**クラス。

## <a name="syntax"></a>構文

```cpp
HString(HSTRING hstr = nullptr) throw();
HString(HString&& other) throw();
```

#### <a name="parameters"></a>パラメーター

*hstr*<br/>
HSTRING ハンドルの場合。

*other*<br/>
既存の**HString**オブジェクト。

## <a name="remarks"></a>Remarks

最初のコンス トラクターによって初期化新しい**HString**オブジェクトが空です。

2 番目のコンス トラクターによって初期化、新しい**HString**オブジェクト、既存の値から*他*パラメーター、し、その後破棄、*他*パラメーター。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HString クラス](../windows/hstring-class.md)
---
title: VerifyInheritanceHelper 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2a011b0583d8221ec49d16236add978ac647acc3
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788930"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename I, typename Base>
struct VerifyInheritanceHelper;

template <typename I>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>パラメーター

*I*<br/>
型。

*ベース*<br/>
別の型。

## <a name="remarks"></a>Remarks

1 つのインターフェイスが別のインターフェイスから派生したかどうかをテストします。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

名前                                       | 説明
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[Verifyinheritancehelper::verify](#verify) | 現在のテンプレート パラメーターで指定された 2 つのインターフェイスをテストし、1 つのインターフェイスは、その他から派生されているかどうかを決定します。

## <a name="inheritance-hierarchy"></a>継承階層

`VerifyInheritanceHelper`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="verify"></a>Verifyinheritancehelper::verify

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
static void Verify();
```

### <a name="remarks"></a>Remarks

現在のテンプレート パラメーターで指定された 2 つのインターフェイスをテストし、1 つのインターフェイスは、その他から派生されているかどうかを決定します。

1 つのインターフェイスは、その他から派生していない場合は、エラーが生成されます。

---
title: VerifyInheritanceHelper 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
ms.openlocfilehash: 3650cfb70ffc12572b3965534eff4e1f2ecb2cf5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374228"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename I, typename Base>
struct VerifyInheritanceHelper;

template <typename I>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>パラメーター

*私*<br/>
型。

*ベース*<br/>
別のタイプ。

## <a name="remarks"></a>解説

1 つのインターフェイスが別のインターフェイスから派生しているかどうかをテストします。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

名前                                       | 説明
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[継承ヘルパーを確認::検証](#verify) | 現在のテンプレート パラメーターで指定された 2 つのインターフェイスをテストし、一方のインターフェイスが他方のインターフェイスから派生しているかどうかを判断します。

## <a name="inheritance-hierarchy"></a>継承階層

`VerifyInheritanceHelper`

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="verifyinheritancehelperverify"></a><a name="verify"></a>継承ヘルパーを確認::検証

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
static void Verify();
```

### <a name="remarks"></a>解説

現在のテンプレート パラメーターで指定された 2 つのインターフェイスをテストし、一方のインターフェイスが他方のインターフェイスから派生しているかどうかを判断します。

一方のインターフェイスが他方のインターフェイスから派生していない場合は、エラーが発生します。

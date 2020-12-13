---
description: '詳細については、次を参照してください: VerifyInheritanceHelper 構造体'
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
ms.openlocfilehash: 672455482a2d21cb695124cad31740b6325c377d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135045"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

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

*常用*<br/>
別の型。

## <a name="remarks"></a>解説

あるインターフェイスが別のインターフェイスから派生しているかどうかをテストします。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

名前                                       | 説明
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[VerifyInheritanceHelper:: Verify](#verify) | 現在のテンプレートパラメーターによって指定された2つのインターフェイスをテストし、一方のインターフェイスが他方のインターフェイスから派生しているかどうかを判断します。

## <a name="inheritance-hierarchy"></a>継承階層

`VerifyInheritanceHelper`

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft:: WRL::D etails

## <a name="verifyinheritancehelperverify"></a><a name="verify"></a> VerifyInheritanceHelper:: Verify

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
static void Verify();
```

### <a name="remarks"></a>解説

現在のテンプレートパラメーターによって指定された2つのインターフェイスをテストし、一方のインターフェイスが他方のインターフェイスから派生しているかどうかを判断します。

あるインターフェイスがもう一方のインターフェイスから派生していない場合、エラーが生成されます。

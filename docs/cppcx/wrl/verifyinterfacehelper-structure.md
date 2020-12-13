---
description: '詳細情報: VerifyInterfaceHelper 構造体'
title: VerifyInterfaceHelper 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInterfaceHelper structure
- Microsoft::WRL::Details::VerifyInterfaceHelper::Verify method
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
ms.openlocfilehash: a9b51eac55666d15b8362fc070d0feb731e9674d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135032"
---
# <a name="verifyinterfacehelper-structure"></a>VerifyInterfaceHelper 構造体

は、Windows ランタイム C++ テンプレートライブラリインフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <bool isWinRTInterface, typename I>
struct VerifyInterfaceHelper;

template <typename I>
struct VerifyInterfaceHelper<false, I>;
```

### <a name="parameters"></a>パラメーター

*I*<br/>
検証するインターフェイス。

*isWinRTInterface*

## <a name="remarks"></a>解説

テンプレートパラメーターによって指定されたインターフェイスが特定の要件を満たしていることを確認します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

名前                                            | 説明
----------------------------------------------- | ---------------------------------------------------------------------------------------------------
[VerifyInterfaceHelper::Verify メソッド](#verify) | 現在のテンプレートパラメーターによって指定されたインターフェイスが特定の要件を満たしていることを確認します。

## <a name="inheritance-hierarchy"></a>継承階層

`VerifyInterfaceHelper`

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft:: WRL::D etails

## <a name="verifyinterfacehelperverify"></a><a name="verify"></a> VerifyInterfaceHelper:: Verify

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
static void Verify();
```

### <a name="remarks"></a>解説

現在のテンプレートパラメーターによって指定されたインターフェイスが特定の要件を満たしていることを確認します。

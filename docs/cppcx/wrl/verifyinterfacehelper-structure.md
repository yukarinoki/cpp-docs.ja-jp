---
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
ms.openlocfilehash: 09c2cc7e08e2dc0e8df42c64d285c37627c5925a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374247"
---
# <a name="verifyinterfacehelper-structure"></a>VerifyInterfaceHelper 構造体

Windows ランタイム C++ テンプレート ライブラリ インフラストラクチャをサポートし、コードから直接使用することを意図していません。

## <a name="syntax"></a>構文

```cpp
template <bool isWinRTInterface, typename I>
struct VerifyInterfaceHelper;

template <typename I>
struct VerifyInterfaceHelper<false, I>;
```

### <a name="parameters"></a>パラメーター

*私*<br/>
検証するインターフェイス。

*インターフェイス*

## <a name="remarks"></a>解説

テンプレート パラメーターで指定されたインターフェイスが特定の要件を満たしていることを確認します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

名前                                            | 説明
----------------------------------------------- | ---------------------------------------------------------------------------------------------------
[VerifyInterfaceHelper::Verify メソッド](#verify) | 現在のテンプレート パラメーターで指定されたインターフェイスが特定の要件を満たしていることを確認します。

## <a name="inheritance-hierarchy"></a>継承階層

`VerifyInterfaceHelper`

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="verifyinterfacehelperverify"></a><a name="verify"></a>インターフェイスヘルパー::検証

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
static void Verify();
```

### <a name="remarks"></a>解説

現在のテンプレート パラメーターで指定されたインターフェイスが特定の要件を満たしていることを確認します。

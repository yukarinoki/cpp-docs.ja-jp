---
title: VerifyInterfaceHelper 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInterfaceHelper structure
- Microsoft::WRL::Details::VerifyInterfaceHelper::Verify method
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b70155566695ade6b6778ade3b4758faebb3ea67
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788866"
---
# <a name="verifyinterfacehelper-structure"></a>VerifyInterfaceHelper 構造体

Windows ランタイム C++ テンプレート ライブラリのインフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <bool isWinRTInterface, typename I>
struct VerifyInterfaceHelper;

template <typename I>
struct VerifyInterfaceHelper<false, I>;
```

### <a name="parameters"></a>パラメーター

*I*<br/>
インターフェイスを確認します。

*isWinRTInterface*

## <a name="remarks"></a>Remarks

テンプレート パラメーターで指定されたインターフェイスが特定の要件を満たしていることを確認します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

名前                                            | 説明
----------------------------------------------- | ---------------------------------------------------------------------------------------------------
[VerifyInterfaceHelper::Verify メソッド](#verify) | 現在のテンプレート パラメーターで指定されたインターフェイスが特定の要件を満たしていることを確認します。

## <a name="inheritance-hierarchy"></a>継承階層

`VerifyInterfaceHelper`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="verify"></a>Verifyinterfacehelper::verify

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
static void Verify();
```

### <a name="remarks"></a>Remarks

現在のテンプレート パラメーターで指定されたインターフェイスが特定の要件を満たしていることを確認します。

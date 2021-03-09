---
description: '詳細については、次を参照してください: no_sanitize_address'
title: no_sanitize_address
ms.date: 11/04/2016
f1_keywords:
- no_sanitize_address__cpp
helpviewer_keywords:
- __declspec keyword [C++], no_sanitize_address
- no_sanitize_address __declspec keyword
ms.openlocfilehash: a18b60f666bc53ef72db3a6d230dc7531cc6bc1f
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471199"
---
# `no_sanitize_address`

**Microsoft 固有の仕様**

**`__declspec(no_sanitize_address)`** 指定子は、関数、ローカル変数、またはグローバル変数のアドレスサニタイザーを無効にするようにコンパイラに指示します。 この指定子は、 [AddressSanitizer](../sanitizers/asan.md)と組み合わせて使用されます。

> [!NOTE]
> **`__declspec(no_sanitize_address)`***実行時* の動作ではなく、_コンパイラ_ の動作を無効にします。

## <a name="example"></a>例

例については、「 [AddressSanitizer build reference](../sanitizers/asan-building.md#__declspecno_sanitize_address) 」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`__declspec`](../cpp/declspec.md)\
[Keywords](../cpp/keywords-cpp.md)\
[AddressSanitizer](../sanitizers/asan.md)

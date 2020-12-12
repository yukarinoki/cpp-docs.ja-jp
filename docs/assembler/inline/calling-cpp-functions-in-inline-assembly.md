---
description: 詳細については、「インラインアセンブリでの C++ 関数の呼び出し」を参照してください。
title: インライン アセンブリでの C++ 関数の呼び出し
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
ms.openlocfilehash: 3efd4f00eae5810b287a27546bba3160f479b8f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117966"
---
# <a name="calling-c-functions-in-inline-assembly"></a>インライン アセンブリでの C++ 関数の呼び出し

**Microsoft 固有の仕様**

ブロックは、 **`__asm`** オーバーロードされていないグローバル C++ 関数のみを呼び出すことができます。 オーバーロードされたグローバル C++ 関数または C++ メンバー関数を呼び出すと、コンパイラはエラーを発行します。

**Extern "C"** リンケージで宣言されたすべての関数を呼び出すこともできます。 これにより、 **`__asm`** すべての標準ヘッダーファイルで **Extern "C"** リンケージを持つライブラリ関数が宣言されるため、C++ プログラム内のブロックで c ライブラリ関数を呼び出すことができます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インラインアセンブラー](../../assembler/inline/inline-assembler.md)<br/>

---
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
ms.openlocfilehash: 781b60c8973593039c0fdfa2f457170e95048597
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192536"
---
# <a name="calling-c-functions-in-inline-assembly"></a>インライン アセンブリでの C++ 関数の呼び出し

**Microsoft 固有の仕様**

ブロックは、 **`__asm`** オーバーロードされていないグローバル C++ 関数のみを呼び出すことができます。 オーバーロードされたグローバル C++ 関数または C++ メンバー関数を呼び出すと、コンパイラはエラーを発行します。

**Extern "C"** リンケージで宣言されたすべての関数を呼び出すこともできます。 これにより、 **`__asm`** すべての標準ヘッダーファイルで**Extern "C"** リンケージを持つライブラリ関数が宣言されるため、C++ プログラム内のブロックで c ライブラリ関数を呼び出すことができます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インラインアセンブラー](../../assembler/inline/inline-assembler.md)<br/>

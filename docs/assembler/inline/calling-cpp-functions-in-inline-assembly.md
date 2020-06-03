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
ms.openlocfilehash: f16e466ebb5f31231411eaaf9a1a85bfcc46a34d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169579"
---
# <a name="calling-c-functions-in-inline-assembly"></a>インライン アセンブリでの C++ 関数の呼び出し

**Microsoft 固有の仕様**

`__asm` ブロックは、オーバーロードされC++ていないグローバル関数のみを呼び出すことができます。 オーバーロードされたグローバルC++関数またはC++メンバー関数を呼び出すと、コンパイラはエラーを発行します。

**Extern "C"** リンケージで宣言されたすべての関数を呼び出すこともできます。 これにより、すべての標準C++ヘッダーファイルで**extern "C"** リンケージを持つライブラリ関数が宣言されるため、プログラム内の `__asm` ブロックで C ライブラリ関数を呼び出すことができます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[インライン アセンブラー](../../assembler/inline/inline-assembler.md)<br/>

---
title: 呼び出し規約 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9e65dfd7f7cff25debd8eb0d00a7e3bb0397692
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410893"
---
# <a name="calling-conventions"></a>呼び出し規則
Visual C/C++ コンパイラには、内部関数と外部関数の呼び出し規約がいくつか用意されています。 これらの異なる方法を理解することは、プログラムをデバッグし、コードをアセンブリ言語ルーチンとリンクするときに役立ちます。  
  
 この話題に関するトピックでは、呼び出し規約の違い、引数の渡し方、関数による値の返し方について説明します。 naked 関数の呼び出し (独自のプロローグおよびエピローグ コードを記述できる高度な機能) についても説明します。  
  
 X64 呼び出し規則については、プロセッサを参照してください[呼び出し規約](../build/calling-convention.md)です。  
  
## <a name="topics-in-this-section"></a>このセクションのトピック  
  
-   [引数を渡すと名前付け規則](../cpp/argument-passing-and-naming-conventions.md)(`__cdecl`、 `__stdcall`、 `__fastcall`、およびその他)  
  
-   [呼び出しの例: 関数プロトタイプと呼び出し](../cpp/calling-example-function-prototype-and-call.md)  
  
-   [Naked 関数の呼び出しを使用してカスタム プロローグ/エピローグ コードを記述するには](../cpp/naked-function-calls.md)  
  
-   [浮動小数点コプロセッサと呼び出し規約](../cpp/floating-point-coprocessor-and-calling-conventions.md)  
  
-   [廃止された呼び出し規約](../cpp/obsolete-calling-conventions.md)  
  
## <a name="see-also"></a>関連項目  
 [Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)
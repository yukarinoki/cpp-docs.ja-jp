---
title: 引数の渡し規則と名前付け規則 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- argument passing [C++], conventions
- arguments [C++], widening
- coding conventions, arguments
- arguments [C++], passing
- registers, return values
- thiscall keyword [C++]
- naming conventions [C++], arguments
- arguments [C++], naming
- passing arguments [C++], conventions
- conventions [C++], argument names
ms.assetid: de468979-eab8-4158-90c5-c198932f93b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43aa3430b641f6333c6c35d618f9e9de123b7390
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413487"
---
# <a name="argument-passing-and-naming-conventions"></a>引数の渡し規則と名前付け規則
**Microsoft 固有の仕様**  
  
 Visual C++ コンパイラでは、関数と呼び出し元の間の、引数と戻り値の受け渡しに関する規約を指定することができます。 サポートされるすべてのプラットフォームですべての規約がサポートされるわけではありません。また、一部の規約は、プラットフォーム固有の実装を使用します。 ほとんどの場合、特定のプラットフォームでサポートされていない規約を指定するキーワードやコンパイラ スイッチは無視され、プラットフォームの既定の規約が使用されます。  
  
 x86 プラットフォームでは、すべての引数は渡されたときに 32 ビットに拡大変換されます。 EDX:EAX レジスタ ペアに返される 8 バイトの構造体を除き、戻り値も 32 ビットに拡張され、EAX レジスタに返されます。 より大きな構造体は、非表示の戻り値の構造体へのポインターとして EAX レジスタに返されます。 パラメーターは、スタックに右から左へプッシュされます。 POD ではない構造体はレジスタ内では返されません。  
  
 コンパイラは、関数で ESI、EDI、EBX、および EBP レジスタが使用されている場合、それらを保存および復元するためにプロローグ コードとエピローグ コードを生成します。  
  
> [!NOTE]
>  構造体、共用体、またはクラスが値渡しで関数から戻される場合は、型のすべての定義が同じである必要があります。そうでないと、実行時にプログラムが失敗することがあります。  
  
 独自の関数プロローグおよびエピローグ コードを定義する方法については、次を参照してください。 [Naked 関数の呼び出し](../cpp/naked-function-calls.md)です。  
  
 ターゲット x64 プラットフォームでは、「コードの呼び出し規則について、既定値は[x64 の概要については呼び出し規約](../build/overview-of-x64-calling-conventions.md)です。 ARM プラットフォームを対象とするコードの呼び出し規約問題については、次を参照してください。[一般的な Visual c ARM 移行に関する問題](../build/common-visual-cpp-arm-migration-issues.md)です。  
  
 次の呼び出し規則は Visual C/C++ コンパイラでサポートされます。  
  
|キーワード|スタック クリーンアップ|パラメーター渡し|  
|-------------|-------------------|-----------------------|  
|[__cdecl](../cpp/cdecl.md)|Caller|パラメーターをスタックに逆の順序で (右から左に) プッシュする|  
|[__clrcall](../cpp/clrcall.md)|N/A|CLR 式スタックに順に (左から右に) パラメーターを読み込む|  
|[__stdcall](../cpp/stdcall.md)|Callee|パラメーターをスタックに逆の順序で (右から左に) プッシュする|  
|[__fastcall](../cpp/fastcall.md)|Callee|レジスタに格納されてから、スタックにプッシュされる|  
|[__thiscall](../cpp/thiscall.md)|Callee|スタックにプッシュされます。**この**ECX に格納されているポインター|  
|[__vectorcall](../cpp/vectorcall.md)|Callee|レジスタに格納されてから、スタックに逆の順序で (右から左に) プッシュされる|  
  
 関連情報については、次を参照してください。[廃止された呼び出し規約](../cpp/obsolete-calling-conventions.md)です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規約](../cpp/calling-conventions.md)
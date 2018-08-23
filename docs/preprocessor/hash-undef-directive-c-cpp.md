---
title: '#undef ディレクティブ (C/C++) |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#undef'
dev_langs:
- C++
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c98c6559e04f0e89fa4c3501f30cd88d449de306
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538448"
---
# <a name="undef-directive-cc"></a>#undef ディレクティブ (C/C++)
`#define` で作成された名前を削除 (定義解除) します。  
  
## <a name="syntax"></a>構文  
  
```  
#undef   
identifier  
```  
  
## <a name="remarks"></a>Remarks 

**#Undef**ディレクティブの現在の定義を削除します*識別子*します。 その結果、後続の*識別子*はプリプロセッサによって無視されます。 使用してマクロ定義を削除する **#undef**のマクロのみ*識別子*; パラメーター リストが得られない。  
  
適用することも、 **#undef**ディレクティブを以前の定義を持たない識別子。 これにより、その識別子が未定義であることが保証されます。 内ではマクロ置換は実行されません **#undef**ステートメント。  
  
**#Undef**ディレクティブと組み合わせるは通常、`#define`識別子が必要がある特別な意味をソース プログラムに領域を作成するディレクティブ。 たとえば、ソース プログラムの特定の関数でマニフェスト定数を使用すると、プログラムの残り部分に影響を与えない環境固有の値を定義できます。 **#Undef**ディレクティブでも使用できます、`#if`ディレクティブをソース プログラムの条件付きコンパイルを制御します。 参照してください[#if、#elif、#else、および #endif ディレクティブ](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)詳細についてはします。  
  
次の例では、 **#undef**ディレクティブは、シンボリック定数およびマクロの定義を削除します。 マクロの識別子のみが指定されていることに注意してください。  
  
```  
#define WIDTH 80  
#define ADD( X, Y ) ((X) + (Y))  
.  
.  
.  
#undef WIDTH  
#undef ADD  
```  
  
**Microsoft 固有の仕様**  
  
マクロを使用してコマンドラインからに定義できます、`/U`オプションを定義するマクロ名を続けています。 このコマンドを発行の効果は一連の`#undef`*マクロ名*ステートメントをファイルの先頭にあります。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 
[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)
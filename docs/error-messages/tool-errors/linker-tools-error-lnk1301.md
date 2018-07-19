---
title: リンカ ツール エラー LNK1301 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1301
dev_langs:
- C++
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b4e298ad3815c741ff6c901ac39bf7838ed135d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299706"
---
# <a name="linker-tools-error-lnk1301"></a>リンカ ツール エラー LNK1301
LTCG clr モジュールが見つかると、/LTCG:parameter と互換性がありません。  
  
 /Clr:pure および/GL でコンパイルされたモジュールは、/LTCG の (PGO) パラメーターをプロファイル ガイド付き最適化のいずれかと共にリンカーに渡されました。  
  
 /Clr:pure モジュールでは、プロファイル ガイド付き最適化はサポートされていません。  
  
 詳細については次を参照してください:  
  
-   [/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [/LTCG (リンク時のコード生成)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  /Clr でコンパイルしないでまたは/LTCG を PGO パラメーターのいずれかとリンクしません。  
  
## <a name="example"></a>例  
 次の例では、LNK1301 が生成されます。  
  
```  
// LNK1301.cpp  
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj  
// LNK1301 expected  
class MyClass {  
public:  
   int i;  
};  
```
---
title: C 宣言と定義 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c459999ab902a2498d4ffe4cc2d437a0a432b9b7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="c-declarations-and-definitions"></a>C 宣言と定義
"宣言" では、特定の変数、関数、型、およびその属性の間の関連付けが設定されます。 非終端要素である `declaration` の ANSI 構文については、「[宣言の概要](../c-language/overview-of-declarations.md)」で説明しています。 宣言では、識別子にいつどこでアクセスできるか (識別子の "リンケージ") も指定されます。 リンケージについては、「[有効期間、スコープ、可視性、およびリンケージ](../c-language/lifetime-scope-visibility-and-linkage.md)」をご覧ください。  
  
 変数の "定義" では宣言と同じ関連付けが設定されますが、さらに、変数にストレージが割り当てられます。  
  
 たとえば、`main`、`find`、`count` の各関数と、`var` 変数および `val` 変数が、1 つのソース ファイルに次の順序で定義されているとします。  
  
```  
int main() {}  
  
int var = 0;  
double val[MAXVAL];  
char find( fileptr ) {}  
int count( double f ) {}  
```  
  
 変数 `var` および `val` は、それ以上の宣言がなくても、`find` 関数と `count` 関数で使用できます。 しかし、これらの名前は `main` からは認識されません (アクセスできません)。  
  
## <a name="see-also"></a>参照  
 [ソース ファイルとソース プログラム](../c-language/source-files-and-source-programs.md)
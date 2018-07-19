---
title: 型と変数サイズ インライン アセンブリで |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- length
- Type
dev_langs:
- C++
helpviewer_keywords:
- variables, length
- size, getting in inline assembly
- size
- LENGTH operator
- TYPE operator
- SIZE operator
- inline assembly, operators
- variables, type
- variables, size
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3466158c507e618e701df5aed35db7e5814abe52
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050593"
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>インライン アセンブリでの型と変数サイズ
**Microsoft 固有の仕様**  
  
 **長さ**、**サイズ**、および**型**演算子は、インライン アセンブリで制限の意味を持ちます。 まったく使用できない、`DUP`演算子 (MASM ディレクティブまたは演算子を使用してデータを定義することはできません) ためです。 それらを使用して、C または C++ の変数または型のサイズを検索することができます。  
  
-   **長さ**演算子は、配列内の要素の数を返すことができます。 非配列変数の値 1 を返します。  
  
-   **サイズ**演算子は、C または C++ の変数のサイズを返すことができます。 変数のサイズは、製品の**長さ**と**型**です。  
  
-   **型**演算子は、C または C++ の型または変数のサイズを返すことができます。 変数が配列では、**型**配列の 1 つの要素のサイズを返します。  
  
 たとえば、プログラムがある 8 要素`int`配列、  
  
```  
int arr[8];  
```  
  
 C とアセンブリの式は次のサイズの返さ`arr`とその要素。  
  
|__asm|C|サイズ|  
|-------------|-------|----------|  
|**長さ**arr|`sizeof`(arr)/`sizeof`(arr[0])|8|  
|**サイズ**arr|`sizeof`(arr)|32|  
|**型**arr|`sizeof`(arr[0])|4|  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)
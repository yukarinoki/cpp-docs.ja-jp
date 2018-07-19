---
title: コンパイラ エラー C2002 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01124fc839d6e788ff2dccae325f01f7d4337f5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164867"
---
# <a name="compiler-error-c2002"></a>コンパイラ エラー C2002
無効なワイド文字定数  
  
 マルチバイト文字定数が正しくありません。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  ワイド文字定数には、予想よりも多くのバイト数が含まれています。  
  
2.  標準ヘッダー STDDEF.h は含まれません。  
  
3.  ワイド文字は、通常のリテラル文字列と連結ことはできません。  
  
4.  ワイド文字定数は、文字 'L' 続く必要があります。  
  
    ```  
    L'mbconst'  
    ```  
  
5.  Microsoft C プリプロセッサ ディレクティブのテキストの引数は ASCII である必要があります。 たとえば、次のようなディレクティブがあると、 `#pragma message(L"string")`、無効です。
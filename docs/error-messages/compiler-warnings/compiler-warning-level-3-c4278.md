---
title: コンパイラの警告 (レベル 3) C4278
ms.date: 08/27/2018
f1_keywords:
- C4278
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
ms.openlocfilehash: 7994ae05d6cb16b5ddc9775b1044de7f3a22d542
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174233"
---
# <a name="compiler-warning-level-3-c4278"></a>コンパイラの警告 (レベル 3) C4278

> '*identifier*': タイプライブラリ '*tlb*' の識別子は既にマクロです。' rename ' 修飾子を使用します

[#Import](../../preprocessor/hash-import-directive-cpp.md)を使用する場合、インポートする typelib 内の識別子が識別子*識別子*を宣言しようとしています。 ただし、これは既に有効なシンボルです。

タイプライブラリのシンボルにエイリアスを割り当てるには、`#import` **rename**属性を使用します。

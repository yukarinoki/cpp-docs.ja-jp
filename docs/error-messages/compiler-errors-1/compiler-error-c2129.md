---
title: コンパイラ エラー C2129
ms.date: 11/04/2016
f1_keywords:
- C2129
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
ms.openlocfilehash: a3e2268bfc5597668e8689d093a0c2bb7f18e037
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80207286"
---
# <a name="compiler-error-c2129"></a>コンパイラ エラー C2129

静的関数 ' function ' が宣言されましたが、定義されていません。

定義されていない `static` 関数に前方参照が行われています。

`static` 関数は、ファイルスコープ内で定義する必要があります。 関数が別のファイルで定義されている場合は、`extern`として宣言する必要があります。

---
title: コンパイラ エラー C2129
ms.date: 11/04/2016
f1_keywords:
- C2129
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
ms.openlocfilehash: 9cf414200dcfad8ae617e16e111bd26b19a315a6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220432"
---
# <a name="compiler-error-c2129"></a>コンパイラ エラー C2129

静的関数 ' function ' が宣言されましたが、定義されていません。

定義されていない関数への前方参照が行われ **`static`** ます。

関数は、 **`static`** ファイルスコープ内で定義する必要があります。 関数が別のファイルで定義されている場合は、その関数を宣言する必要があり **`extern`** ます。

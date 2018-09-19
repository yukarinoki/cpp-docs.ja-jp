---
title: コンパイラ エラー C2129 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2129
dev_langs:
- C++
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e86515a7d7c8954271578291c4ebcb1a52fc9863
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054286"
---
# <a name="compiler-error-c2129"></a>コンパイラ エラー C2129

静的関数 'function' が宣言されていますが、定義されていません

前方参照される、`static`定義されていない関数です。

A`static`ファイルのスコープ内で関数を定義する必要があります。 宣言する必要があります、関数は、別のファイルで定義されているが場合、`extern`します。
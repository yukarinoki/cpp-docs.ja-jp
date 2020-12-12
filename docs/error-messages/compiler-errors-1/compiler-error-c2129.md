---
description: 詳細については、「コンパイラエラー C2129」を参照してください。
title: コンパイラ エラー C2129
ms.date: 11/04/2016
f1_keywords:
- C2129
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
ms.openlocfilehash: 5efb19aa3f4edd14dd6cfab93c3880745b08e59d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323156"
---
# <a name="compiler-error-c2129"></a>コンパイラ エラー C2129

静的関数 ' function ' が宣言されましたが、定義されていません。

定義されていない関数への前方参照が行われ **`static`** ます。

関数は、 **`static`** ファイルスコープ内で定義する必要があります。 関数が別のファイルで定義されている場合は、その関数を宣言する必要があり **`extern`** ます。

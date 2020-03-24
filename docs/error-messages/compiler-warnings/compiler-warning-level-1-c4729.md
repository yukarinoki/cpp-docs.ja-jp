---
title: コンパイラの警告 (レベル 1) C4729
ms.date: 11/04/2016
f1_keywords:
- C4729
helpviewer_keywords:
- C4729
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
ms.openlocfilehash: e78606f117251fa8ab1f08f2cef280a266309c32
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185829"
---
# <a name="compiler-warning-level-1-c4729"></a>コンパイラの警告 (レベル 1) C4729

フロー グラフ ベースの警告の関数が大きすぎます。

この警告が生成されるのは、関数が大きすぎてコンパイルできず、警告を生成する状況を確実にチェックできない場合です。 この警告は、 [/Od](../../build/reference/od-disable-debug.md) コンパイラ オプションを使用している場合にのみ生成されます。

この警告を解決するには、関数を小さい関数に分割します。

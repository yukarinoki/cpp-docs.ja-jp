---
title: コンパイラ エラー C2170
ms.date: 11/04/2016
f1_keywords:
- C2170
helpviewer_keywords:
- C2170
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
ms.openlocfilehash: 828e5bbca0b796864ec8b364ee69c18a3b5eea00
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206954"
---
# <a name="compiler-error-c2170"></a>コンパイラ エラー C2170

' identifier ': 関数として宣言されていません。組み込みにすることはできません

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. プラグマ `intrinsic` は、関数以外の項目に対して使用されています。

1. プラグマ `intrinsic` は、組み込みフォームがない関数に使用されます。

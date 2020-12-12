---
description: 詳細については、「コンパイラエラー C2170」を参照してください。
title: コンパイラ エラー C2170
ms.date: 11/04/2016
f1_keywords:
- C2170
helpviewer_keywords:
- C2170
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
ms.openlocfilehash: 2f6093221d214aa12f6b90f40dde14518e44e08e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322259"
---
# <a name="compiler-error-c2170"></a>コンパイラ エラー C2170

' identifier ': 関数として宣言されていません。組み込みにすることはできません

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. プラグマ `intrinsic` は、関数以外の項目に対して使用されています。

1. プラグマ `intrinsic` は、組み込みフォームがない関数に使用されます。

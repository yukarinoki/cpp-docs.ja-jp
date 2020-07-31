---
title: コンパイラ エラー C3552
ms.date: 11/04/2016
f1_keywords:
- C3552
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
ms.openlocfilehash: d2d3a60fcd4a26238cd6cf330f47b48c5b3198ad
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230832"
---
# <a name="compiler-error-c3552"></a>コンパイラ エラー C3552

'typename': 遅延指定の戻り値の型に 'auto' を含めることはできません

**`auto`** 関数の戻り値の型のプレースホルダーとしてキーワードを使用する場合は、遅延指定の戻り値の型を指定する必要があります。 ただし、別のキーワードを使用し **`auto`** て、遅延指定の戻り値の型を指定することはできません。 たとえば、次のコード フラグメントはエラー C3552 を生成します。

`auto myFunction->auto; // C3552`

---
description: 詳細については、「コンパイラエラー C3552」を参照してください。
title: コンパイラ エラー C3552
ms.date: 11/04/2016
f1_keywords:
- C3552
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
ms.openlocfilehash: aca1474f53c8ac1a8257b23d0042550b76b3c0e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223257"
---
# <a name="compiler-error-c3552"></a>コンパイラ エラー C3552

'typename': 遅延指定の戻り値の型に 'auto' を含めることはできません

**`auto`** 関数の戻り値の型のプレースホルダーとしてキーワードを使用する場合は、遅延指定の戻り値の型を指定する必要があります。 ただし、別のキーワードを使用し **`auto`** て、遅延指定の戻り値の型を指定することはできません。 たとえば、次のコード フラグメントはエラー C3552 を生成します。

`auto myFunction->auto; // C3552`

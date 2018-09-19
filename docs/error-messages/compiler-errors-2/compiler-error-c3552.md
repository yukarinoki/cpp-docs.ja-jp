---
title: コンパイラ エラー C3552 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3552
dev_langs:
- C++
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd9f7ae37500e115fa33fa61298cab800c88f9c7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081261"
---
# <a name="compiler-error-c3552"></a>コンパイラ エラー C3552

'typename': 遅延指定の戻り値の型に 'auto' を含めることはできません

関数の戻り値の型のプレース ホルダーとして `auto` キーワードを使用する場合は、遅延指定の戻り値の型を指定する必要があります。 ただし、別の `auto` キーワードを使用して遅延指定の戻り値の型を指定することはできません。 たとえば、次のコード フラグメントはエラー C3552 を生成します。

`auto myFunction->auto; // C3552`
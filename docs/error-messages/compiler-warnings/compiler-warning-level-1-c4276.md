---
description: '詳細情報: コンパイラの警告 (レベル 1) C4276'
title: コンパイラの警告 (レベル 1) C4276
ms.date: 11/04/2016
f1_keywords:
- C4276
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
ms.openlocfilehash: 14b13b2eb1e13d28f2b208e52ef71e1c729fe5e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311787"
---
# <a name="compiler-warning-level-1-c4276"></a>コンパイラの警告 (レベル 1) C4276

' function ': プロトタイプが指定されていません。パラメーターを想定しない

[__Stdcall](../../cpp/stdcall.md)呼び出し規約を使用して関数のアドレスを取得する場合は、コンパイラが関数の装飾名を作成できるように、プロトタイプを指定する必要があります。 *関数* にはプロトタイプがないため、装飾名を作成するときのコンパイラは、関数にパラメーターがないことを前提としています。

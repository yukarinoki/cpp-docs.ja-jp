---
description: 詳細については、「コンパイラエラー C2773」を参照してください。
title: コンパイラエラー C2773
ms.date: 11/04/2016
f1_keywords:
- C2773
helpviewer_keywords:
- C2773
ms.assetid: 8d564b26-1623-4d92-aabc-dff33f7b1145
ms.openlocfilehash: 4530257adab91abec8a1fa87f8625ef6dbd7bb04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298241"
---
# <a name="compiler-error-c2773"></a>コンパイラエラー C2773

\#インポートと #using は C++ コンパイラでのみ使用できます

C コンパイラはプリプロセッサディレクティブを認識しません `#import` 。 ソースを C++ としてコンパイルします。 必要に応じて、 [/tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) を使用します。

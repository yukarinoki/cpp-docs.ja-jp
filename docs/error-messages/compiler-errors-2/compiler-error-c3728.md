---
description: 詳細については、「コンパイラエラー C3728」を参照してください。
title: コンパイラ エラー C3728
ms.date: 11/04/2016
f1_keywords:
- C3728
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
ms.openlocfilehash: 0cfcbd38928a153e3f5a58c1ec66b7e1c5bfd08d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245097"
---
# <a name="compiler-error-c3728"></a>コンパイラ エラー C3728

' event ': イベントに raise メソッドがありません

C# などの言語で作成されたメタデータでは、イベントが定義されたクラスの外部から発生することはできません。また、 [#using](../../preprocessor/hash-using-directive-cpp.md) ディレクティブに含まれていました。また、CLR プログラミングを使用する Visual C++ プログラムは、イベントを発生させようとしました。

C# などの言語で開発されたプログラムでイベントを発生させるには、イベントを含むクラスで、イベントを発生させるパブリックメソッドも定義する必要があります。

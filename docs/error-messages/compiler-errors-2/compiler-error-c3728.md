---
title: コンパイラ エラー C3728
ms.date: 11/04/2016
f1_keywords:
- C3728
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
ms.openlocfilehash: 8aec3ae1ff629ef7fa000182cde29e306a471315
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165875"
---
# <a name="compiler-error-c3728"></a>コンパイラ エラー C3728

' event ': イベントに raise メソッドがありません

などの言語C#で作成されたメタデータでは、イベントが定義されたクラスの外部から発生することはできません。また、 [#using](../../preprocessor/hash-using-directive-cpp.md)ディレクティブに含まれC++ています。また、CLR プログラミングを使用するビジュアルプログラムは、イベントを発生させようとしました。

などC#の言語で開発されたプログラムでイベントを発生させるには、イベントを含むクラスで、イベントを発生させるパブリックメソッドも定義する必要があります。

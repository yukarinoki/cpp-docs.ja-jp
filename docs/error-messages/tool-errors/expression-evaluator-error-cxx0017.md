---
title: 式エバリュエーター エラー CXX0017
ms.date: 11/04/2016
f1_keywords:
- CXX0017
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
ms.openlocfilehash: 64ebce0161d67c298d55095f6bc409820120c34a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196015"
---
# <a name="expression-evaluator-error-cxx0017"></a>式エバリュエーター エラー CXX0017

シンボルが見つかりません

式に指定されたシンボルが見つかりませんでした。

このエラーの考えられる原因の1つは、シンボル名の大文字と小文字の不一致です。 C とはC++大文字と小文字が区別される言語であるため、シンボル名は、ソースで定義されているのと同じように指定する必要があります。

このエラーは、デバッグ中に変数を監視するために変数を型キャストしようとすると発生することがあります。 `typedef` が型の新しい名前を宣言していますが、新しい型が定義されていません。 デバッガーで実行しようとした型キャストには、定義された型の名前が必要です。

このエラーは CAN0017 と同じです。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策

1. シンボルが、使用されているプログラムのポイントで既に宣言されていることを確認します。

1. 実際の型名を使用して、`typedef`定義の名前ではなく、デバッガーで変数をキャストします。

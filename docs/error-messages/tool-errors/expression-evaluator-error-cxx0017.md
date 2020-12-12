---
description: 詳細については、「式エバリュエーターエラー CXX0017」を参照してください。
title: 式エバリュエーター エラー CXX0017
ms.date: 11/04/2016
f1_keywords:
- CXX0017
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
ms.openlocfilehash: 0abb99422383f95e13d4137a5ad899730d485f87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228275"
---
# <a name="expression-evaluator-error-cxx0017"></a>式エバリュエーター エラー CXX0017

シンボルが見つかりません

式に指定されたシンボルが見つかりませんでした。

このエラーの考えられる原因の1つは、シンボル名の大文字と小文字の不一致です。 C と C++ は大文字と小文字が区別される言語であるため、シンボル名は、ソースで定義されているのと同じように指定する必要があります。

このエラーは、デバッグ中に変数を監視するために変数を型キャストしようとすると発生することがあります。 は、 `typedef` 型の新しい名前を宣言していますが、新しい型を定義していません。 デバッガーで実行しようとした型キャストには、定義された型の名前が必要です。

このエラーは CAN0017 と同じです。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. シンボルが、使用されているプログラムのポイントで既に宣言されていることを確認します。

1. 定義された名前ではなく、実際の型名を使用してデバッガーで変数をキャストし `typedef` ます。

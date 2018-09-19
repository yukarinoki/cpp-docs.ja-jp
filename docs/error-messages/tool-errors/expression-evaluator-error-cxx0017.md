---
title: 式エバリュエーター エラー CXX0017 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0017
dev_langs:
- C++
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 431071137fb3f5b1b276327ee7d21f323ac24c5b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136245"
---
# <a name="expression-evaluator-error-cxx0017"></a>式エバリュエーター エラー CXX0017

シンボルが見つかりません

式で指定されたシンボルが見つかりませんでした。

このエラーの考えられる原因の 1 つは、シンボル名の大文字と小文字が一致しません。 C および C++ 言語の区別があるため、ソースで定義されている大文字小文字の区別のシンボル名を与える必要があります。

このエラーは、デバッグ中に、変数を監視するために変数を型キャストしようとするときに発生することができます。 `typedef`型の新しい名前を宣言しますが、新しい型を定義しません。 型キャスト、デバッガーで試行すると、定義された型の名前が必要です。

このエラーは、can0017 と同じものと同じです。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. シンボルが既に位置が使用中のプログラムで宣言されていることを確認します。

1. 実際の型名を使用して、デバッガーで変数をキャストではなく`typedef`-定義名。
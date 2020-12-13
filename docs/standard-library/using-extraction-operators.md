---
description: 詳細については、「抽出演算子の使用」を参照してください。
title: 抽出演算子の使用
ms.date: 11/04/2016
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
ms.openlocfilehash: 11115ed9d7f83b5e4d8cefe088c638afe8d95f38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153578"
---
# <a name="using-extraction-operators"></a>抽出演算子の使用

抽出演算子 (`>>`) はすべての標準 C++ データ型に対してあらかじめプログラミングされており、入力ストリーム オブジェクトからバイトを取得する最も簡単な方法となります。

書式設定テキスト入力抽出演算子は、受信するデータ値の区切りが余白文字であることを前提としています。 テキスト フィールドに複数の単語が含まれている場合や、数字がカンマで区切られている場合に、このことは不便です。 このような場合は、代わりに、書式設定されていない入力メンバー関数 [istream::getline](../standard-library/basic-istream-class.md#getline) を使用して、余白が含まれたテキストのブロックを読み取り、その後、特殊関数でブロックを解析するという方法があります。 別の方法として、`GetNextToken` などのメンバー関数を使用して入力ストリーム クラスを派生させることで、istream メンバーを呼び出し、文字データを抽出して書式設定できます。

## <a name="see-also"></a>関連項目

[入力ストリーム](../standard-library/input-streams.md)

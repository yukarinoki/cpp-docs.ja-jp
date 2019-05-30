---
title: ML エラー メッセージ
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
ms.openlocfilehash: adf2c509c3d8d9110ddb757f809a4bca9199df7a
ms.sourcegitcommit: af580f3a11b19d22288424eac7ceae1bc24ab312
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66355325"
---
# <a name="ml-error-messages"></a>ML エラー メッセージ

MASM のコンポーネントによって生成されるエラー メッセージは、3 つのカテゴリに分類されます。

- **致命的なエラー。** ユーティリティが、通常のプロセスを完了するを防ぎます深刻な問題を示します。

- **致命的でないエラー。** ユーティリティは、そのプロセスを完了可能性があります。 その場合、その結果は希望する可能性があります。

- **警告です。** これらのメッセージは、目的の結果を取得できない可能性がある条件を示します。

すべてのエラー メッセージは、次の形式をとります。

> *ユーティリティ*:*ファイル名*(*行*): {*Error_type*} (*コード*)。*Message_text*

それぞれの文字について以下に説明します。

*ユーティリティ*<br/>
エラー メッセージを送信したプログラムです。

*ファイル名*<br/>
エラーが発生元条件を含むファイルです。

*Line*<br/>
おおよその行では、エラー条件が存在します。

*Error_type*<br/>
致命的なエラー、エラー、または警告。

*コード*<br/>
一意の 5 または 6 桁のエラー コード。

*テキスト*<br/>
短期保存と一般的なエラー状態の説明です。

## <a name="see-also"></a>関連項目

[Microsoft Macro Assembler リファレンス](../../assembler/masm/microsoft-macro-assembler-reference.md)

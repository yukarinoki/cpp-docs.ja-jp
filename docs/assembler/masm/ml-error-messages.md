---
title: ML エラー メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
dev_langs:
- C++
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 836daf438fa5a7f4c797b5b15ffab89720a7af98
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43675966"
---
# <a name="ml-error-messages"></a>ML エラー メッセージ

MASM のコンポーネントによって生成されるエラー メッセージは、3 つのカテゴリに分類されます。

- **致命的なエラー。** ユーティリティが、通常のプロセスを完了するを防ぎます深刻な問題を示します。

- **致命的でないエラー。** ユーティリティは、そのプロセスを完了可能性があります。 その場合、その結果は希望する可能性があります。

- **警告です。** これらのメッセージは、目的の結果を取得できない可能性がある条件を示します。

すべてのエラー メッセージは、次の形式をとります。

> *ユーティリティ*: *Filename* (*行*): {*Error_type*} (*コード*):*テキスト*

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

[Microsoft Macro Assembler リファレンス](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>
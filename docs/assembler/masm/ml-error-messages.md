---
description: '詳細情報: ML エラーメッセージ'
title: ML エラー メッセージ
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- vc.errors.ml
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
ms.openlocfilehash: 08f9a3ccd1bfe79195bf3ba9acf5b5347cc35a1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129702"
---
# <a name="ml-error-messages"></a>ML エラー メッセージ

MASM コンポーネントによって生成されるエラーメッセージは、次の3つのカテゴリに分類されます。

- **致命的なエラー。** これらは、ユーティリティが通常のプロセスを完了できないような重大な問題を示しています。

- **致命的でないエラー。** ユーティリティのプロセスが完了する場合があります。 その場合、結果が必要なものではない可能性があります。

- **付.** これらのメッセージは、必要な結果を得られない可能性のある条件を示します。

すべてのエラーメッセージは次の形式になります。

> *ユーティリティ*: *ファイル名* (*行*): {*Error_type*} (*コード*): *Message_text*

ここで、

*ユーティリティ*\
エラーメッセージを送信したプログラム。

*/Db*\
エラー生成条件を含むファイルです。

*直線*\
エラー状態が存在するおおよその行。

*Error_type*\
致命的なエラー、エラー、または警告。

*コード*\
5桁または6桁の一意のエラーコード。

*Message_text*\
エラー状態の概要と一般的な説明。

## <a name="see-also"></a>関連項目

[Microsoft マクロアセンブラーリファレンス](microsoft-macro-assembler-reference.md)

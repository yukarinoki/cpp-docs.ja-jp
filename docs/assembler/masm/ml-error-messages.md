---
title: ML エラー メッセージ
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- vc.errors.ml
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
ms.openlocfilehash: 2db928d22219d33f89396bb29530680d4b3c8dba
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856944"
---
# <a name="ml-error-messages"></a>ML エラー メッセージ

MASM コンポーネントによって生成されるエラーメッセージは、次の3つのカテゴリに分類されます。

- **致命的なエラー。** これらは、ユーティリティが通常のプロセスを完了できないような重大な問題を示しています。

- **致命的でないエラー。** ユーティリティのプロセスが完了する場合があります。 その場合、結果が必要なものではない可能性があります。

- **付.** これらのメッセージは、必要な結果を得られない可能性のある条件を示します。

すべてのエラーメッセージは次の形式になります。

> *ユーティリティ*:*ファイル名*(*行*): {*Error_type*} (*コード*): *Message_text*

ここで、

*ユーティリティ*\
エラーメッセージを送信したプログラム。

*ファイル名*\
エラー生成条件を含むファイルです。

*行*\
エラー状態が存在するおおよその行。

*Error_type*\
致命的なエラー、エラー、または警告。

*コード*\
5桁または6桁の一意のエラーコード。

*Message_text*\
エラー状態の概要と一般的な説明。

## <a name="see-also"></a>参照

[Microsoft マクロアセンブラーリファレンス](../../assembler/masm/microsoft-macro-assembler-reference.md)

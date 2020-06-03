---
title: コマンド ライン エラー D8037
ms.date: 11/04/2016
f1_keywords:
- D8037
helpviewer_keywords:
- D8037
ms.assetid: acddaaa0-bd84-426f-a37b-8f680b379c9d
ms.openlocfilehash: ed6778861c89bb9755087c4d58f094a57d5f760f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196860"
---
# <a name="command-line-error-d8037"></a>コマンド ライン エラー D8037

一時 il ファイルを作成できません。古い il ファイルの一時ディレクトリを消去します

一時コンパイラの中間ファイルを作成するための十分な領域がありません。 このエラーを解決するには、 **TMP**環境変数で指定されたディレクトリ内の古い MSIL ファイルをすべて削除します。 これらのファイルは _CL_hhhhhhhh. ss の形式になります。 h はランダムな16進数を表し、ss は IL ファイルの種類を表します。 また、必ず最新のオペレーティングシステムの修正プログラムを使用してコンピューターを更新してください。

## <a name="see-also"></a>参照

[コマンド ライン エラー D8000 から D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC コンパイラ オプション](../../build/reference/compiler-options.md)

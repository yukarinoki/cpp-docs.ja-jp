---
title: ML の致命的でないエラー A2006 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2006
dev_langs:
- C++
helpviewer_keywords:
- A2006
ms.assetid: b8a8f096-95df-42b5-85ed-d2530560a84c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f287c6ab46c6af71ba6dc0032f332ce3cc489454
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43677406"
---
# <a name="ml-nonfatal-error-a2006"></a>ML の致命的でないエラー A2006

**未定義のシンボル: 識別子**

定義されていないシンボルの使用が試行されました。

次のいずれかが発生した可能性があります。

- シンボルが定義されていません。

- フィールドの指定された構造体のメンバーでした。

- シンボルは含まれていなかったインクルード ファイルで定義されました。

- 外部シンボルを使用していない、 [EXTERN](../../assembler/masm/extern-masm.md)または[EXTERNDEF](../../assembler/masm/externdef.md)ディレクティブ。

- シンボル名が間違っています。

- ローカル コード ラベルは、そのスコープの外部で参照されました。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>
---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: c8ea49b9862159a5a56bfb3d2c3cd0c1f4cd7413
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596873"
---
# <a name="local-masm"></a>LOCAL (MASM)

、マクロ内の最初のディレクティブで**ローカル**マクロの各インスタンスに固有のラベルを定義します。

## <a name="syntax"></a>構文

> ローカル*localname* [、 *localname*].

> ローカル*ラベル*[*カウント*]] [:*型*] [、*ラベル*[*カウント*]] [*型*]].

## <a name="remarks"></a>Remarks

プロシージャ定義内で、次のディレクティブ (**PROC**)、**ローカル**プロシージャの実行中に存在するスタック ベースの変数を作成します。 *ラベル*単純な変数か、配列を含む可能性があります*カウント*要素。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
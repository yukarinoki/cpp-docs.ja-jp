---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 94af498865151ff5c49fac9dbc03de65c4ecb934
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327604"
---
# <a name="local-masm"></a>LOCAL (MASM)

、マクロ内の最初のディレクティブで**ローカル**マクロの各インスタンスに固有のラベルを定義します。

## <a name="syntax"></a>構文

> ローカル*localname* \[、 *localname*].
>
> ローカル*ラベル* \[ __\[__*カウント*__]__ ] \[ __:__ *型*] \[ __、__ *ラベル* \[ __\[__*カウント*__]__ ] \[*型*].

## <a name="remarks"></a>Remarks

プロシージャ定義内で、次のディレクティブ (**PROC**)、**ローカル**プロシージャの実行中に存在するスタック ベースの変数を作成します。 *ラベル*単純な変数か、配列を含む可能性があります*カウント*要素。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
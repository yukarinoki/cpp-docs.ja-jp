---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 94af498865151ff5c49fac9dbc03de65c4ecb934
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62178008"
---
# <a name="local-masm"></a>LOCAL (MASM)

、マクロ内の最初のディレクティブで**ローカル**マクロの各インスタンスに固有のラベルを定義します。

## <a name="syntax"></a>構文

> LOCAL *localname* \[, *localname*] ...
>
> ローカル*ラベル* \[ __\[__*カウント*__]__ ] \[ __:__ *型*] \[ __、__ *ラベル* \[ __\[__*カウント*__]__ ] \[*型*].

## <a name="remarks"></a>Remarks

プロシージャ定義内で、次のディレクティブ (**PROC**)、**ローカル**プロシージャの実行中に存在するスタック ベースの変数を作成します。 *ラベル*単純な変数か、配列を含む可能性があります*カウント*要素。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
---
title: ローカル (MASM) |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Local
dev_langs:
- C++
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8105bc8168ce28d468a1378c5cf7889907a7c9f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685064"
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
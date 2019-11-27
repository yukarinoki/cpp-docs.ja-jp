---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: c3a04f68b7fd17b2b6459c219a98fd99ec2d62d4
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397251"
---
# <a name="local-masm"></a>LOCAL (MASM)

最初のディレクティブでは、マクロ内で、マクロの各インスタンスに固有のラベル**を定義し**ます。

## <a name="syntax"></a>構文

> **LOCAL** *localname* ⟦、 *localname* ...⟧
>
> **LOCAL** *label* ⟦ __\[__ *count* __]__ ⟧⟦ __:__ *type*⟧⟦ __,__ *label* ⟦ __\[__ *count* __]__ ⟧⟦*type*⟧...⟧

## <a name="remarks"></a>コメント

2番目のディレクティブでは、プロシージャ定義 (**PROC**) 内で、プロシージャの実行中に存在するスタックベースの変数を**ローカル**で作成します。 *ラベル*は、単純な変数または*count*要素を含む配列にすることができます。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)

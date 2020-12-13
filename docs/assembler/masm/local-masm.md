---
description: '詳細情報: ローカル'
title: LOCAL (MASM)
ms.date: 12/16/2019
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 27296f69b62de0dcd314b2575f045e06576bbf64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129754"
---
# <a name="local"></a>LOCAL

最初のディレクティブでは、マクロ内で、マクロの各インスタンスに固有のラベル **を定義し** ます。

## <a name="syntax"></a>構文

> **LOCAL** *LocalId* ⟦、 *localId* ...⟧
>
> **LOCAL** *lab⟦ d* __\[__ *count*__]__ ⟧⟦__:__*qualifiedType*⟧⟦__,__ *lab d* ⟦ __\[__ *count*__]__ ⟧⟦*qualifiedType*⟧...⟧

## <a name="remarks"></a>解説

2番目のディレクティブでは、プロシージャ定義 (**PROC**) 内で、プロシージャの実行中に存在するスタックベースの変数を **ローカル** で作成します。 *Labに* は、単純な変数または *count* 要素を含む配列を指定できます。 *count* は定数式です。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

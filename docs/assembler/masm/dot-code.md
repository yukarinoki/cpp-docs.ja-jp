---
title: .CODE
ms.date: 08/30/2018
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: a5b6608ca71a2b406c54a06cd44ac2865211a8ac
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398578"
---
# <a name="code"></a>.CODE

と共に使用[します。モデル](../../assembler/masm/dot-model.md)は、コードセグメントの開始を示します。

## <a name="syntax"></a>構文

> **.CODE** ⟦*name*⟧

### <a name="parameters"></a>パラメーター

*名前*\
コードセグメントの名前を指定する省略可能なパラメーターです。 既定の名前は、小さい、小さい、コンパクト、およびフラット[モデル](../../assembler/masm/dot-model.md)の場合に **_TEXT**ます。 既定の名前は、他のモデルの場合は*modulename*_TEXT です。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](../../assembler/masm/directives-reference.md)\
[.DATA](../../assembler/masm/dot-data.md)

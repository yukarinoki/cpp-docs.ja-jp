---
title: .CODE
ms.date: 12/06/2019
f1_keywords:
- .CODE
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
ms.openlocfilehash: 36d9c01d2a24b446ddc91fe73f3cb677067b3e4c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "74987921"
---
# <a name="code-32-bit-masm"></a>.コード (32 ビット MASM)

と共に使用[します。モデル](../../assembler/masm/dot-model.md)は、コードセグメントの開始を示します。

## <a name="syntax"></a>構文

> **.CODE** ⟦*name*⟧

### <a name="parameters"></a>パラメーター

*名前*\
コードセグメントの名前を指定する省略可能なパラメーターです。 既定の名前は、小さい、小さい、コンパクト、およびフラット[モデル](../../assembler/masm/dot-model.md)の場合に **_TEXT**ます。 既定の名前は、他のモデルの場合は*modulename*_TEXT です。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](../../assembler/masm/directives-reference.md)\
[.DATA](../../assembler/masm/dot-data.md)

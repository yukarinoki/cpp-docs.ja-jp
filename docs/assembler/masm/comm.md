---
title: COMM
ms.date: 12/06/2019
f1_keywords:
- COMM
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
ms.openlocfilehash: 93e7c891b1c964eca5b3ff7fd15956ef25ea05e6
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "74987948"
---
# <a name="comm"></a>COMM

*定義*で指定された属性を使用して、communal 変数を作成します。

## <a name="syntax"></a>構文

> **COMM** *definition* ⟦ __、__ *定義*...⟧

## <a name="remarks"></a>Remarks

Communal 変数はリンカーによって割り当てられるため、初期化できません。 つまり、このような変数の場所やシーケンスに依存することはできません。

各*定義*には、次の形式があります。

⟦*言語-* 型⟧⟦**NEAR** | **FAR**⟧ _label_ **:** _type_⟦ **:** _count_⟧

*言語型*、 **NEAR**、および**FAR**引数は、32ビット MASM でのみ有効です。

省略可能な*言語の種類*は、次の名前の名前付け規則を設定します。 によって指定されたすべての言語をオーバーライド**します。モデル**ディレクティブ。 省略可能な**NEAR**または**FAR**は、現在のメモリモデルをオーバーライドします。 *ラベル*は変数の名前です。 *型*には、任意の型指定子 ([BYTE](../../assembler/masm/byte-masm.md)、 [WORD](../../assembler/masm/word.md)など)、またはバイト数を指定する整数を指定できます。 省略可能な*カウント*は、宣言されたデータオブジェクト内の要素の数を指定します。 既定の*カウント*は1です。

## <a name="example"></a>使用例

この例では、512バイトの要素の配列を作成します。

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)

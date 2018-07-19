---
title: COMM |Microsoft ドキュメント
ms.custom: ''
ms.date: 05/22/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1df6c729ab130a7ff38d7f7cf83224e7425e7dba
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2018
ms.locfileid: "34463024"
---
# <a name="comm"></a>COMM

指定された属性を持つ土台変数を作成*定義*です。

## <a name="syntax"></a>構文

> **COMM** *定義*[、*定義*].

## <a name="remarks"></a>コメント

土台変数は、リンカーによって割り当てられているし、初期化できません。 つまり、場所またはそのような変数の順序に依存していることはできません。

各*定義*は次の形式があります。

[*langtype*] [**NEAR** &#124; **FAR**]_ラベル_**:**_型_[**:**_カウント_]

省略可能な*langtype*に続く名前の命名規則を設定します。 指定された任意の言語をオーバーライドし、**です。モデル**ディレクティブです。 省略可能な**NEAR**または**FAR**メモリの現在のモデルをオーバーライドします。 *ラベル*変数の名前を指定します。 *型*任意の型指定子を指定できます ([バイト](../../assembler/masm/byte-masm.md)、 [WORD](../../assembler/masm/word.md)など) またはバイト数を指定する整数。 省略可能な*カウント*宣言されたデータ オブジェクトの要素の数を指定します。 既定値は 1 つです。

## <a name="example"></a>例

この例では、512 バイトの要素の配列を作成します。

```masm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)

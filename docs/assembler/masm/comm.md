---
title: 通信 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
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
ms.openlocfilehash: 87bf6d91de052d7ecaf637100b455e66819c748b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43690033"
---
# <a name="comm"></a>COMM

指定された属性を持つ土台の変数を作成します。*定義*します。

## <a name="syntax"></a>構文

> **通信***定義*[、*定義*].

## <a name="remarks"></a>Remarks

土台の変数は、リンカーによって割り当てられているし、初期化することはできません。 これは、場所やこのような変数の順序に依存できないことを意味します。

各*定義*は次の形式があります。

[*langtype*] [**NEAR** &#124; **FAR**]_ラベル_**:**_型_[**:**_カウント_]

省略可能な*langtype*に続く名前の名前付け規則を設定します。 指定された任意の言語よりも優先、**します。モデル**ディレクティブ。 省略可能な**NEAR**または**FAR**現在のメモリ モデルをオーバーライドします。 *ラベル*変数の名前を指定します。 *型*任意の型指定子を指定できます ([バイト](../../assembler/masm/byte-masm.md)、 [WORD](../../assembler/masm/word.md)など) またはバイト数を指定する整数。 省略可能な*カウント*宣言されたデータ オブジェクトの要素の数を指定します。 既定値は 1 つです。

## <a name="example"></a>例

この例では、512 バイトの要素の配列を作成します。

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>

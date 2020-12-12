---
description: 詳細情報:/disasm
title: /DISASM
ms.date: 01/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: 764754e017958a57afd53236b7fc1ffb6217d850
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192903"
---
# <a name="disasm"></a>/DISASM

DUMPBIN 出力のコードセクションの逆アセンブリを出力します。

## <a name="syntax"></a>構文

> **/DISASM**{**:** \[ **BYTES** | **NOBYTES**]}

### <a name="arguments"></a>引数

**メモリ**<br/>
命令バイトを、解釈されたオペコードおよび逆アセンブリ出力の引数と共に含めます。 既定のオプションです。

**NOBYTES**<br/>
には、逆アセンブリ出力に命令バイトが含まれていません。

## <a name="remarks"></a>解説

**/Disasm** オプションは、ファイルのコードセクションの逆アセンブリを表示します。 デバッグシンボルがファイル内に存在する場合は、これを使用します。

**/Disasm** は、ネイティブで管理されていないイメージでのみ使用する必要があります。 マネージコードに相当するツールは、 [ildasm.exe](/dotnet/framework/tools/ildasm-exe-il-disassembler)です。

[/Gl (プログラム全体の最適化)](gl-whole-program-optimization.md)コンパイラオプションで生成されたファイルで使用できるのは、 [/HEADERS](headers.md) DUMPBIN オプションだけです。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](dumpbin-options.md)

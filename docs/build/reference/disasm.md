---
title: /DISASM
ms.date: 1/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: 77f6f05029ec4480afb2180eab0bb57838d643a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462947"
---
# <a name="disasm"></a>/DISASM

DUMPBIN 出力内のコード セクションの逆アセンブリを出力します。

## <a name="syntax"></a>構文

> **/DISASM**{**:**\[**バイト**|**NOBYTES**]}

### <a name="arguments"></a>引数

**BYTES**<br/>
逆アセンブリの出力には、解釈されたオペコードと引数と共に命令のバイトが含まれています。 これは、既定の設定です。

**NOBYTES**<br/>
逆アセンブリの出力には命令のバイトは含まれません。

## <a name="remarks"></a>Remarks

**/DISASM**オプションが、ファイルのコード セクションの逆アセンブルを表示します。 ファイルに含まれている場合は、デバッグ シンボルを使用します。

**/DISASM**ネイティブで管理されていないイメージでのみ使用する必要があります。 マネージ コード用の同等のツールは[ILDASM](/dotnet/framework/tools/ildasm-exe-il-disassembler)します。

のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションがによって生成されたファイルで使用できる、 [/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)

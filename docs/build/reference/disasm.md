---
title: /DISASM |Microsoft Docs
ms.date: 1/17/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /disasm
dev_langs:
- C++
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a5a4d930c47d2a3c2808cbd0a343c5c68de4ac9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707188"
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

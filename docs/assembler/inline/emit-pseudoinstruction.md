---
title: _emit 疑似命令
ms.date: 08/30/2018
f1_keywords:
- _emit
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
ms.openlocfilehash: 8be250aadf20dc4a7dee6a0b565ece21840339d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169475"
---
# <a name="_emit-pseudoinstruction"></a>_emit 疑似命令

**Microsoft 固有の仕様**

**_Emit**擬似命令は、現在のテキストセグメントの現在位置に1バイトを定義します。 **_Emit**擬似命令は、MASM の[DB](../../assembler/masm/db.md)ディレクティブに似ています。

次のフラグメントは、バイト0x4A、0x4a、および0X4a をコードに配置します。

```cpp
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B
.
.
.
__asm {
    randasm
    }
```

> [!CAUTION]
> `_emit` がレジスタを変更する命令を生成し、最適化を使用してアプリケーションをコンパイルした場合、コンパイラは影響を受けるレジスタを特定できません。 たとえば、`_emit` が**rax**レジスタを変更する命令を生成した場合、コンパイラは**rax**が変更されたことを認識しません。 その後、コンパイラは、インラインアセンブラーコードの実行後に、レジスタ内の値について誤った想定を行う可能性があります。 その結果、アプリケーションの実行時に予期しない動作が発生する可能性があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>

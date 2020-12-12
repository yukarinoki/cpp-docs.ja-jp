---
description: 詳細については、「_emit 擬似命令」を参照してください。
title: _emit 疑似命令
ms.date: 08/30/2018
f1_keywords:
- _emit
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
ms.openlocfilehash: d3e2a39312c94ff0e4868bed9afa74011051a129
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117810"
---
# <a name="_emit-pseudoinstruction"></a>_emit 疑似命令

**Microsoft 固有の仕様**

**_Emit** 擬似命令は、現在のテキストセグメントの現在位置に1バイトを定義します。 **_Emit** 擬似命令は、MASM の [DB](../../assembler/masm/db.md)ディレクティブに似ています。

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
> が `_emit` レジスタを変更する命令を生成し、最適化を使用してアプリケーションをコンパイルした場合、コンパイラは影響を受けるレジスタを特定できません。 たとえば、によって `_emit` **rax** register を変更する命令が生成された場合、コンパイラは **rax** が変更されたことを認識しません。 その後、コンパイラは、インラインアセンブラーコードの実行後に、レジスタ内の値について誤った想定を行う可能性があります。 その結果、アプリケーションの実行時に予期しない動作が発生する可能性があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>

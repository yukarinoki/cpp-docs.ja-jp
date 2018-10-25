---
title: _emit 疑似命令 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- _emit
dev_langs:
- C++
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 569e3a078109e66df7dcf5cbf314817ce0786899
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061927"
---
# <a name="emit-pseudoinstruction"></a>_emit 疑似命令

**Microsoft 固有の仕様**

**_Emit**疑似命令は、現在のテキスト セグメントで、現在の場所にある 1 バイトを定義します。 **_Emit**疑似命令に似ています、 [DB](../../assembler/masm/db.md)の MASM ディレクティブ。

次のフラグメントでは、コードに 0x4A、0x43、および 0x4B バイトを配置します。

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
> 場合`_emit`命令を生成レジスタを変更する、最適化を使用してアプリケーションをコンパイルして、コンパイラがどのようなレジスタが影響を受けるを判断することはできません。 たとえば場合、`_emit`を変更する命令を生成、 **rax**レジスタをコンパイラでは不明です**rax**が変更されました。 コンパイラは、登録インライン アセンブラー コードの実行後にその値の詳細について不適切な想定を行うし可能性があります。 その結果、アプリケーションは、実行時に、予期しない動作を示す可能性があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
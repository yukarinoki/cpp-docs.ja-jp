---
title: BufferCommand 列挙型
description: 'CMemFile:: GetBufferPtr () を使用してメモリファイルを操作するために使用される BufferCommand 列挙について説明します。'
ms.date: 07/23/2020
f1_keywords:
- afx/buffercommand
helpviewer_keywords:
- buffercommand enumeration [MFC]
ms.openlocfilehash: f2f553df56fadd99b65b04cce9a97917425ed70b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212074"
---
# <a name="buffercommand-enumeration"></a>BufferCommand 列挙型

[CMemFile:: GetBufferPtr](cmemfile-class.md#getbufferptr)によって使用され、ファイルによってサポートされるメモリバッファーに対して実行するアクションを決定します。

## <a name="syntax"></a>構文

``` cpp
public enum BufferCommand
{
   bufferRead,
   bufferWrite,
   bufferCommit,
   bufferCheck
};
```

## <a name="members"></a>メンバー

|名前|説明|
|-|-|
| `bufferRead` | ファイルによってサポートされるメモリバッファーを読み取ります。 |
| `bufferWrite` | ファイルによってサポートされるメモリバッファーに書き込みます。 |
| `bufferCommit` | ファイルを格納するメモリバッファー内の現在位置を、コミットされたバッファーの末尾に進めます。 |
| `bufferCheck` | ファイルによってサポートされるメモリバッファーのサイズを増やすことができるかどうかを判断します。 |

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)

---
title: OPTION (MASM)
ms.date: 08/30/2018
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: 0f90ab0115c3dde894d468bbbe60ffa0193b8336
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74395168"
---
# <a name="option-masm"></a>OPTION (MASM)

アセンブラーの機能を有効または無効にします。

## <a name="syntax"></a>構文

> **オプションオプション**の*一覧*

## <a name="remarks"></a>コメント

使用可能なオプションには次のものがあります。

|||||
|-|-|-|-|
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**エミュレーター**|
|**NOEMULATOR**|**エピローグ**|**EXPR16**|**EXPR32**|
|**言語**|**LJMP**|**NOLJMP**|**M510**|
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**影**|
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|
|**PROC**|**プロローグ**|**READONLY**|**NOREADONLY**|
|**役割**|**NOSCOPED**|**SEGMENT**|**SETIF2**。|

言語の構文は、 **OPTION language:** <em>x</em>です。ここで、 *x*は C、SYSCALL、STDCALL、PASCAL、FORTRAN、または BASIC.  SYSCALL、PASCAL、FORTRAN、および BASIC は、ではサポートされていません[。モデル](../../assembler/masm/dot-model.md)フラット。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)

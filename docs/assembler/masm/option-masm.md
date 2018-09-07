---
title: オプション (MASM) |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- option
dev_langs:
- C++
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09db749baf09525957faaf8af99434cc9775d0e7
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678046"
---
# <a name="option-masm"></a>OPTION (MASM)

有効にし、アセンブラーの機能を無効にします。

## <a name="syntax"></a>構文

> オプション*optionlist*

## <a name="remarks"></a>Remarks

使用可能なオプションは次のとおりです。

|||||
|-|-|-|-|
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**エミュレーター**|
|**NOEMULATOR**|**EPILOGUE**|**EXPR16**|**EXPR32**|
|**言語**|**LJMP**|**NOLJMP**|**M510**|
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|
|**PROC**|**プロローグ**|**READONLY**|**NOREADONLY**|
|**スコープ**|**NOSCOPED**|**SEGMENT**|**SETIF2**します。|

言語の構文は、**オプション言語:**<em>x</em>ここで、 *x* C、SYSCALL、STDCALL、PASCAL、FORTRAN、BASIC のいずれかです。  SYSCALL や PASCAL、FORTRAN、BASIC ではサポートされません併用[します。モデル](../../assembler/masm/dot-model.md)フラットです。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
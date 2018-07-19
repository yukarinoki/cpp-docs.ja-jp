---
title: オプション (MASM) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 80291c805cad3ef041fffc58983ff399da07c9d9
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057722"
---
# <a name="option-masm"></a>OPTION (MASM)
有効にして、アセンブラーの機能を無効になります。  
  
## <a name="syntax"></a>構文  
  
```  
  
OPTION   
optionlist  
  
```  
  
## <a name="remarks"></a>コメント  
 使用可能なオプションは次のとおりです。  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**エミュレーター**|  
|**NOEMULATOR**|**EPILOGUE**|**EXPR16**|**EXPR32**|  
|**言語**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**プロローグ**|**READONLY**|**NOREADONLY**|  
|**スコープ**|**NOSCOPED**|**SEGMENT**|**SETIF2**です。|  
  
 言語の構文は、**オプション言語: * * * x*ここで、 *x* C、SYSCALL、STDCALL、PASCAL、FORTRAN、または BASIC の 1 つです。  SYSCALL、PASCAL、FORTRAN、および BASIC ではサポートされません併用[です。モデル](../../assembler/masm/dot-model.md)フラットです。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)
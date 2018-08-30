---
title: .FPO |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .FPO
dev_langs:
- C++
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 234ec5bd703a390d1e2ee60e48d99d346d4aad95
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203114"
---
# <a name="fpo"></a>.FPO
します。FPO ディレクティブは、.debug$ セグメントまたはセクションをデバッグ レコードの生成を制御します。  
  
## <a name="syntax"></a>構文  
  
```  
  
FPO (  
cdwLocals  
,   
cdwParams  
,   
cbProlog  
,   
cbRegs  
,   
fUseBP  
,   
cbFrame  
)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cdwLocals`  
 ローカル変数を符号なし 32 ビット値の数。  
  
 `cdwParams`  
 DWORD を符号なし 16 ビット値でパラメーターのサイズ。  
  
 *cbProlog*  
 符号なし 8 ビット値を関数プロローグ コードのバイト数。  
  
 `cbRegs`  
 保存されたレジスタの数。  
  
 `fUseBP`  
 EBP レジスタが割り当てられているかどうかを示します。 0 または 1。  
  
 *cbFrame*  
 フレームの種類を示します。  参照してください[FPO_DATA](/windows/desktop/api/winnt/ns-winnt-_fpo_data)詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)
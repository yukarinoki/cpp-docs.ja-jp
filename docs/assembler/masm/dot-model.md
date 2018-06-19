---
title: .モデル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .MODEL
dev_langs:
- C++
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2814b1b6cc4483807f77989ff4fbb70929400d6e
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057748"
---
# <a name="model"></a>.MODEL
プログラムのメモリ モデルを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
.MODEL memorymodel [[, langtype]] [[, stackoption]]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `memorymodel`  
 コードとデータのポインターのサイズを決定する必須パラメーターです。  
  
 `langtype`  
 プロシージャおよびパブリック シンボルの呼び出しと名前付け規則を設定する省略可能なパラメーターです。  
  
 `stackoption`  
 省略可能なパラメーターです。  
  
 `stackoption` 場合は使用されません`memorymodel`は`FLAT`します。  
  
 指定する`NEARSTACK`スタック セグメントを 1 つの物理セグメントにグループ化 (`DGROUP`) のデータと共にします。 スタック セグメント レジスタ (`SS`) データ セグメント レジスタと同じアドレスを保持すると見なされます (`DS`)。 `FARSTACK` スタックにはグループ化されません`DGROUP`; したがって`SS`と等しくない`DS`です。  
  
## <a name="remarks"></a>コメント  
 .`MODEL` 使用されていない[x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)です。  
  
 次の表は、16 ビットおよび 32 ビットのプラットフォームを対象とする場合に、各パラメーターの値を示します。  
  
|パラメーター|32 ビット値|16 ビット値 (16 ビットの以前の開発のサポート)|  
|---------------|--------------------|----------------------------------------------------------------|  
|`memorymodel`|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|  
|`langtype`|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|  
|`stackoption`|未使用|`NEARSTACK`, `FARSTACK`|  
  
## <a name="code"></a>コード  
 MASM 関連のサンプルでは、サンプルのダウンロード、コンパイラから[Visual C のサンプルおよび関連ドキュメントを Visual Studio 2010 用](http://go.microsoft.com/fwlink/p/?linkid=178749)です。  
  
 次の例での使用、`.MODEL`ディレクティブです。  
  
## <a name="example"></a>例  
  
```  
; file simple.asm  
; For x86 (32-bit), assemble with debug information:   
;   ml -c -Zi simple.asm  
; For x64 (64-bit), assemble with debug information:   
;   ml64 -c -DX64 -Zi simple.asm  
;  
; In this sample, the 'X64' define excludes source not used   
;  when targeting the x64 architecture  
  
ifndef X64  
.686p  
.XMM  
.model flat, C  
endif  
  
.data  
; user data  
  
.code  
; user code  
  
fxn PROC public  
  xor eax, eax ; zero function return value  
  ret  
fxn ENDP  
  
end  
```  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)   
 [Visual C のサンプルおよび関連ドキュメントを Visual Studio 2010 用](http://go.microsoft.com/fwlink/p/?linkid=178749)
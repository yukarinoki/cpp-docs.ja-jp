---
title: セグメント |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- SEGMENT
dev_langs:
- C++
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f5defce11b611f23b67e5e44ac1b9d406f73c0ae
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210420"
---
# <a name="segment"></a>SEGMENT
定義と呼ばれるプログラム セグメント*名前*セグメント属性を持つ  
  
## <a name="syntax"></a>構文  
  
```  
  
   name SEGMENT [[READONLY]] [[align]] [[combine]] [[use]] [[characteristics]] ALIAS(string) [['class']]  
statements  
name ENDS  
```  
  
#### <a name="parameters"></a>パラメーター  
 *align*  
 セグメントの開始アドレスを選択できるメモリ アドレスの範囲。 配置の種類は、次のいずれかにできます。  
  
|配置の種類|開始アドレス|  
|----------------|----------------------|  
|**BYTE**|[次へ] の使用可能なバイトのアドレス。|  
|**WORD**|次に利用可能な word アドレス (2 バイト ワードあたり)。|  
|**DWORD**|次にダブル ワードを使用可能なアドレス (ダブル ワードあたり 4 バイト)。|  
|**PARA**|次の段落が使用可能なアドレス (1 つの段落は 16 バイト)。|  
|**PAGE**|次に利用できるページ アドレス (1 ページあたりの 256 バイト)。|  
|**ALIGN**(*n*)|[次へ] 使用可能な*n*番目のバイトのアドレス。 詳細については「解説」を参照してください。|  
  
 このパラメーターが指定されていない場合**PARA**既定で使用されます。  
  
 *combine*  
 **パブリック**、**スタック**、**共通**、**メモリ**、**で**<em>アドレス</em>、 **プライベート**  
  
 *use*  
 **USE16**、 **USE32**、**フラット**  
  
 `characteristics`  
 **情報**、**読み取り**、**書き込み**、 **EXECUTE**、 **SHARED**、 **NOPAGE**、 **NOCACHE**、および**破棄**  
  
 これら COFF ののみがサポートし、類似した名前の COFF セクション特性に対応しています (たとえば、 **SHARED** IMAGE_SCN_MEM_SHARED に対応しています)。 読み取りは、IMAGE_SCN_MEM_READ フラグを設定します。 古い形式の読み取り専用フラグの原因となった IMG_SCN_MEM_WRITE フラグをクリアするセクション。 存在する場合`characteristics`既定の特性は使用されず、プログラマが指定したフラグのみが有効に設定されます。  
  
 `ALIAS(` `string` `)`  
 この文字列は、生成された COFF オブジェクト内のセクション名として使用されます。  異なる MASM セグメント名では、同じ外部名を複数のセクションを作成します。  
  
 サポートされていません **/omf**します。  
  
 `class`  
 セグメントを結合して、アセンブルされたファイルで順序付けする方法を指定します。 通常、この値は、 `'DATA'`、 `'CODE'`、`'CONST'`と `'STACK'`  
  
## <a name="remarks"></a>Remarks  
 `ALIGN(n)`、`n`は 1 から 8192 の 2 の累乗があります。 でサポートされていません **/omf**します。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)
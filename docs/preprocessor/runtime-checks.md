---
title: runtime_checks |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
dev_langs:
- C++
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b20ea9dd12bfe4daff8e2e440c96a41c220aa742
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541770"
---
# <a name="runtimechecks"></a>runtime_checks
[/RTC](../build/reference/rtc-run-time-error-checks.md) 設定を無効化または復元します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma runtime_checks( "[runtime_checks]", {restore | off} )  
```  
  
## <a name="remarks"></a>Remarks  
 
コンパイラ オプションで有効になっていないランタイム チェックを有効にすることはできません。 たとえば、指定しない場合`/RTCs`を指定して`#pragma runtime_checks( "s", restore)`スタック フレームの検証が有効になりません。  
  
**runtime_checks** プラグマは関数の外に表示する必要があり、プラグマが発生した後に定義される最初の関数で適用されます。 *復元*と*オフ*引数で指定されたオプションを有効にする、 **runtime_checks**を切り替えます。  
  
**Runtime_checks**次の表に示されているパラメーターの 0 個以上にすることができます。  
  
### <a name="parameters-of-the-runtimechecks-pragma"></a>runtime_checks プラグマのパラメーター  
  
|パラメーター|ランタイム チェックの種類|  
|--------------------|-----------------------------|  
|*s*|スタック (フレーム) 検証を有効にします。|  
|*c*|より小さいデータ型に値が代入されてデータが失われる場合に報告します。|  
|*u*|定義する前に変数が使用された場合に報告します。|  
  
使用される同じ文字のうち、`/RTC`コンパイラ オプション。 例えば:  
  
```  
#pragma runtime_checks( "sc", restore )  
```  
  
空の文字列 ( **""** ) での**runtime_checks**プラグマの使用は、ディレクティブの特殊な形式です。  
  
- 使用すると、*オフ*パラメーター、off、上記の表に示す、実行時エラー チェックになります。  
  
- 使用すると、*復元*パラメーターを実行時エラー チェックにリセットされますを指定した、`/RTC`コンパイラ オプション。  
  
```  
#pragma runtime_checks( "", off )  
.  
.  
.  
#pragma runtime_checks( "", restore )   
```  
  
## <a name="see-also"></a>関連項目  
 
[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
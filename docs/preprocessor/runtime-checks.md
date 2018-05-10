---
title: runtime_checks |Microsoft ドキュメント
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
ms.openlocfilehash: 817afaff738b2528bd165e814517c8399cd8a151
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="runtimechecks"></a>runtime_checks
[/RTC](../build/reference/rtc-run-time-error-checks.md) 設定を無効化または復元します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma runtime_checks( "[runtime_checks]", {restore | off} )  
```  
  
## <a name="remarks"></a>コメント  
 コンパイラ オプションで有効になっていないランタイム チェックを有効にすることはできません。 たとえば、/RTCs を指定しない場合、 `#pragma runtime_checks( "s", restore)` を指定すると、スタック フレームの検証は有効になりません。  
  
 **runtime_checks** プラグマは関数の外に表示する必要があり、プラグマが発生した後に定義される最初の関数で適用されます。 **restore** 引数と **off** 引数は *runtime_checks* で指定するオプションのオンとオフを切り替えます。  
  
 *runtime_checks* には、次の表に示すパラメーターの 0 個以上を指定できます。  
  
### <a name="parameters-of-the-runtimechecks-pragma"></a>runtime_checks プラグマのパラメーター  
  
|パラメーター|ランタイム チェックの種類|  
|--------------------|-----------------------------|  
|**s**|スタック (フレーム) 検証を有効にします。|  
|**c**|より小さいデータ型に値が代入されてデータが失われる場合に報告します。|  
|**u**|定義する前に変数が使用された場合に報告します。|  
  
 これらは /RTC コンパイラ オプションで使用される同じ文字です。 例えば:  
  
```  
#pragma runtime_checks( "sc", restore )  
```  
  
 空の文字列 ( **""** ) での**runtime_checks**プラグマの使用は、ディレクティブの特殊な形式です。  
  
-   **off** パラメーターを使用すると、このトピックの前の表で示したランタイム エラー チェックがオフになります。  
  
-   **restore** パラメーターを使用すると、ランタイム エラー チェックが /RTC コンパイラ オプションで指定したランタイム エラー チェックにリセットされます。  
  
```  
#pragma runtime_checks( "", off )  
.  
.  
.  
#pragma runtime_checks( "", restore )   
```  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   

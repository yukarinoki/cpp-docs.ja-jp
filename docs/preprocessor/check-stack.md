---
title: check_stack |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.check_stack
- check_stack_CPP
dev_langs:
- C++
helpviewer_keywords:
- check_stack pragma
- pragmas, check_stack
- pragmas, check_stack usage table
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b393030961aa4695a16a9b50d49d0cae64cc4e0c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="checkstack"></a>check_stack
場合、スタック プローブをオフにするコンパイラに指示**オフ**(または**-**) が指定されている場合、スタック プローブをオンにする、または**で**(または**+**) を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      #pragma check_stack([ {on | off}] )  
#pragma check_stack{+ | -}  
```  
  
## <a name="remarks"></a>コメント  
 引数を指定しない場合、スタック プローブが既定に従って処理されます。 このプラグマは、プラグマの後で定義されている最初の関数に対して効果があります。 スタック プローブは、マクロの一部でも、インラインで生成される関数の一部でもありません。  
  
 引数を指定しない場合、 **check_stack**プラグマによって、スタック チェックは、コマンドラインで指定する動作に戻ります。 詳細については、次を参照してください。[バージョン 4.1 コンパイラ リファレンス](../build/reference/compiler-options.md)です。 相互作用、 **#pragma check_stack**と[/Gs](../build/reference/gs-control-stack-checking-calls.md)オプションが次の表に示します。  
  
### <a name="using-the-checkstack-pragma"></a>check_stack プラグマの使用  
  
|構文|コンパイルで<br /><br /> /Gs オプションを使用?|アクション|  
|------------|------------------------------------|------------|  
|**#pragma check_stack( )** or<br /><br /> **#pragma check_stack**|[はい]|後続の関数のスタック チェックをオフにします|  
|**#pragma check_stack( )** or<br /><br /> **#pragma check_stack**|×|後続の関数のスタック チェックをオンにします|  
|**#pragma check_stack(on)**<br /><br /> または **#pragma check_stack +**|Yes または No|後続の関数のスタック チェックをオンにします|  
|**#pragma check_stack(off)**<br /><br /> または **#pragma check_stack -**|Yes または No|後続の関数のスタック チェックをオフにします|  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
---
title: pointers_to_members |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
dev_langs:
- C++
helpviewer_keywords:
- class members, pointers to
- pragmas, pointers_to_members
- members, pointers to
- pointers_to_members pragma
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 499649e94dbe549deb091291b197c80ff404bc33
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33841393"
---
# <a name="pointerstomembers"></a>pointers_to_members
**C 固有の仕様**  
  
 クラスを定義する前にそのクラスのメンバーへのポインターを宣言できるかどうか、また宣言したポインターを使用してポインターのサイズおよびポインターの解釈に必要なコードを制御するかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma pointers_to_members( pointer-declaration, [most-general-representation] )  
```  
  
## <a name="remarks"></a>コメント  
 配置することができます、 **pointers_to_members**プラグマを使用する代わりに、ソース ファイルで、 [/vmx](../build/reference/vmb-vmg-representation-method.md)コンパイラ オプションまたは[継承キーワード](../cpp/inheritance-keywords.md)です。  
  
 *ポインター宣言*かどうかまたは宣言したポインター メンバーにする前に関連付けられた関数定義の後に引数を指定します。 *ポインター宣言*引数は次の 2 つの記号のいずれか。  
  
|引数|コメント|  
|--------------|--------------|  
|**full_generality**|安全な、場合によっては最適でないコードです。 使用する**full_generality**メンバーへのポインターが関連付けられているクラス定義の前に宣言されている場合。 この引数で指定されたポインター表現を常に使用する、*最も一般的な表現*引数。 これは /vmg と同じです。|  
|**best_case**|メンバーへのすべてのポインターに対し、最適な表現を使用した安全で最適なコードを生成します。 クラスのメンバーへのポインターを宣言する前に、クラスを定義する必要があります。 既定値は**best_case**です。|  
  
 *最も一般的な表現*引数が、コンパイラは、翻訳単位内のクラスのメンバーへのポインターの参照を安全に使用できる最小のポインター表現を指定します。 引数は以下のいずれかになります。  
  
|引数|コメント|  
|--------------|--------------|  
|**single_inheritance**|最も一般的な表現は、単一継承、メンバー関数へのポインターです。 メンバーへのポインターが宣言されているクラス定義の継承モデルが多重継承モデルまたは仮想モデルの場合、エラーが発生します。|  
|**multiple_inheritance**|最も一般的な表現は、多重継承、メンバー関数へのポインターです。 メンバーへのポインターが宣言されているクラス定義の継承モデルが仮想モデルの場合、エラーが発生します。|  
|**virtual_inheritance**|最も一般的な表現は、仮想継承、メンバー関数へのポインターです。 エラーが発生することはありません。 これは、既定の引数と **#pragma pointers_to_members (full_generality)** を使用します。|  
  
> [!CAUTION]
>  `pointers_to_members` プラグマは、影響を与えるソース コード ファイル内のみに指定し、必ず `#include` ディレクティブの後に配置することをお勧めします。 これにより、プラグマが他のファイルに影響を与えるリスクが減少すると共に、同じ変数、関数、またはクラス名に誤って複数の定義を指定するリスクが減少します。  
  
## <a name="example"></a>例  
  
```  
//   Specify single-inheritance only  
#pragma pointers_to_members( full_generality, single_inheritance )  
```  
  
## <a name="end-c-specific"></a>END C++ 固有の仕様  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
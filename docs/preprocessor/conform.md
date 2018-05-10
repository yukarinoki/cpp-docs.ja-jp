---
title: 準拠 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- conform_CPP
- vc-pragma.conform
dev_langs:
- C++
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b145225cfed3131b406d15827b589aed718d16bb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="conform"></a>conform
**C 固有の仕様**  
  
 実行時の動作を指定します、 [/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)コンパイラ オプション。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma conform(name [, show ] [, on | off ] [ [, push | pop ] [, identifier ] ] )  
```  
  
#### <a name="parameters"></a>パラメーター  
 *name*  
 変更されるコンパイラ オプションの名前を指定します。 唯一の有効な*名前*は`forScope`します。  
  
 **表示**(省略可能)  
 現在の設定と、*名前*(true または false)、コンパイル時に警告メッセージとして表示されます。 たとえば、`#pragma conform(forScope, show)` のようにします。  
  
 **on、off**(省略可能)  
 設定*名前*に**で**により、 [/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)コンパイラ オプション。 既定値は**オフ**です。  
  
 **プッシュ**(省略可能)  
 現在の値をプッシュ*名前*を内部コンパイラ スタックにします。 指定する場合*識別子*を指定することができます、**で**または**オフ**値*名*スタックにプッシュされます。 たとえば、`#pragma conform(forScope, push, myname, on)` のようにします。  
  
 **pop** (省略可能)  
 値を設定*名前*を内部コンパイラ スタックし、pop、スタックの上部にある値にします。 識別子が指定されている場合**pop**、レコードが見つかるまでに戻すスタックがポップされます*識別子*がポップされますも; の現在の値*名前*でスタック上の次のレコードの新しい値になります*名前*です。 ポップを指定する場合、*識別子*スタックで、記録されていないこと、 **pop**は無視されます。  
  
 *識別子*(省略可能)  
 付属することができます、**プッシュ**または**pop**コマンド。 場合*識別子*を使用する、**で**または**オフ**指定子も使用できます。  
  
## <a name="example"></a>例  
  
```  
// pragma_directive_conform.cpp  
// compile with: /W1  
// C4811 expected  
#pragma conform(forScope, show)  
#pragma conform(forScope, push, x, on)  
#pragma conform(forScope, push, x1, off)  
#pragma conform(forScope, push, x2, off)  
#pragma conform(forScope, push, x3, off)  
#pragma conform(forScope, show)  
#pragma conform(forScope, pop, x1)  
#pragma conform(forScope, show)  
  
int main() {}  
```  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
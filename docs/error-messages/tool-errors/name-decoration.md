---
title: 装飾の名前を付けます |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- name decoration [C++]
- names [C++], decorated
- decorated names, calling conventions
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e956d0acf9e6debcb183577775e2215e7eccec7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="name-decoration"></a>名前の装飾
名前の装飾は、通常は C++ の名前付け規則を指しますが、C の場合でもよく適用されます。 既定では、C++ では関数名、パラメーター、および戻り値の型を使用して、関数のリンカー名が作成されます。 次の関数について考えてみます。  
  
```  
void CALLTYPE test(void)  
```  
  
 次の表は、さまざまな呼び出し規約のリンカー名を示します。  
  
|呼び出し規約|extern"C"または .c ファイル|.cpp、.cxx、または /TP|  
|------------------------|---------------------------|------------------------|  
|C の名前付け規則 (`__cdecl`)|_test|? @ テスト@ZAXXZ|  
|Fastcall 名前付け規則 (`__fastcall`)|@test@0|? @ テスト@YIXXZ|  
|標準呼び出しの名前付け規則 (`__stdcall`)|_test@0|? @ テスト@YGXXZ|  
|Vectorcall 名前付け規則 (`__vectorcall`)|テストします。@0|? @ テスト@YQXXZ|  
  
 C++ から C の関数を呼び出すには、extern "C" を使用します。 extern "C" を指定すると、クラスに属さない C++ の関数に対しては、C 名前付け規則が適用されます。 コンパイラ スイッチに注意してください **/Tc**または **/Tp**コンパイラ、ファイル名拡張子を無視し、ファイルをそれぞれ C または C++ としてコンパイルするように指示します。 これらのオプションを使用すると、予測した名前にならないことがあります。  
  
 関数プロトタイプのパラメーターが一致していないと、このエラーが発生します。 名前の装飾では、関数のパラメーターを最終の装飾関数名に組み込みます。 関数宣言でのパラメーターと一致していない関数を呼び出すと、LNK2001 が発生することがあります。  
  
 現在では、コンパイラ販売元間またはコンパイラのバージョン間でさえも、C++ の名前付けの規則が確立されていません。 そのため、別のコンパイラでコンパイルされたオブジェクト ファイルをリンクすると、名前付け方式が異なり、外部参照が未解決になります。  
  
## <a name="see-also"></a>関連項目  
 [リンカー ツール エラー LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md)
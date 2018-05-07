---
title: コンパイラの警告 C4394 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4394
dev_langs:
- C++
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05535621443770a2b414f1c4312efbc46e6be858
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4394"></a>コンパイラの警告 C4394
'関数' : appdomain ごとのシンボルは __declspec(dllexport) と共に設定することはできません  
  
 マークされた関数、 [appdomain](../../cpp/appdomain.md) `__declspec`修飾子が MSIL にではなくネイティブ)、およびエクスポート テーブルにコンパイルされる ([エクスポート](../../windows/export.md)`__declspec`修飾子) はマネージ関数のサポートされていません。  
  
 public アクセシビリティを持つようにマネージ関数を宣言できます。 詳細については、次を参照してください。[可視性を入力](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)と[メンバーの可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)です。  
  
 C4394 は、常にエラーとして表示されます。  この警告をオフにすることができます、`#pragma warning`または **/wd**; を参照してください[警告](../../preprocessor/warning.md)または[/w、/W0、/W1、/W2、/W3、/W4、/w1、/w2、/w3、/w4、/Wall、/wd、//wo、/Wv、/WX (警告レベル)](../../build/reference/compiler-option-warning-level.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では、C4394 を生成します。  
  
```  
// C4394.cpp  
// compile with: /clr /c  
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394  
__declspec(dllexport) int g2 = 0;   // OK  
```
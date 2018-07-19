---
title: コンパイラの警告 (レベル 1) C4691 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4691
dev_langs:
- C++
helpviewer_keywords:
- C4691
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9dccce2468c83dd7d14596c1c26e19bd13ad1a70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282598"
---
# <a name="compiler-warning-level-1-c4691"></a>コンパイラの警告 (レベル 1) C4691
'type': 参照されていないアセンブリ 'file'、代わりに使用される現在の翻訳単位で定義された型で参照される型が見つかりました  
  
 元の型定義を含むメタデータ ファイルが参照されていないコンパイラを使用しているローカル型定義。  
  
 場所を再構築する場合は、の*ファイル*、C4691 無視したりプラグマでになっている[警告](../../preprocessor/warning.md)です。  つまり、構築して、ファイル、コンパイラは型定義を見つけ、ファイルと同じである場合は、C4691 を無視できます。  
  
 ただし、予期しない動作発生する可能性がコンパイラでは、同じアセンブリのメタデータで参照されている定義を使用する場合CLR 型は、型の名前だけでなく、アセンブリによっても型指定されます。  つまり、アセンブリ z.dll から型を Z とは異なりますアセンブリ y.dll から型を Z です。  
  
## <a name="example"></a>例  
 このサンプルには、元の型定義が含まれています。  
  
```  
// C4691_a.cpp  
// compile with: /clr /LD /W1  
public ref class Original_Type {};  
```  
  
## <a name="example"></a>例  
 このサンプルでは、C4691_a.dll を参照し、Original_Type の種類のフィールドを宣言します。  
  
```  
// C4691_b.cpp  
// compile with: /clr /LD  
#using "C4691_a.dll"  
public ref class Client {  
public:  
   Original_Type^ ot;  
};  
```  
  
## <a name="example"></a>例  
 次の例では、C4691 が生成されます。  このサンプルが Original_Type の定義が含まれていて、C4691a.dll を参照していません確認します。  
  
 を解決するのには、元の型定義を含むメタデータ ファイルを参照し、ローカル宣言と定義を削除します。  
  
```  
// C4691_c.cpp  
// compile with: /clr /LD /W1  
// C4691 expected  
  
// Uncomment the following line to resolve.  
// #using "C4691_a.dll"  
#using "C4691_b.dll"  
  
// Delete the following line to resolve.  
ref class Original_Type;  
  
public ref class MyClass : Client {};  
```
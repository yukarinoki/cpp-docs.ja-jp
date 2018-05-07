---
title: コンパイラ エラー C3114 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3114
dev_langs:
- C++
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69001d415167f976d0f30c2dd5a0181cc032d0d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3114"></a>コンパイラ エラー C3114
'argument': 名前付き属性引数を有効ではありません  
  
 属性クラスのデータ メンバーを引数の名前が有効にするためには、そのマークしないでください`static`、 `const`、または`literal`です。 プロパティの有効期限がありますいない場合、プロパティを`static`とする必要があります get および set アクセサー。  
  
 詳細については、次を参照してください。[プロパティ](../../windows/property-cpp-component-extensions.md)と[ユーザー定義の属性](../../windows/user-defined-attributes-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3114 を生成します。  
  
```  
// C3114.cpp  
// compile with: /clr /c  
public ref class A : System::Attribute {  
public:  
   static property int StaticProp {  
      int get();  
   }  
  
   property int Prop2 {  
      int get();  
      void set(int i);  
   }  
};  
  
[A(StaticProp=123)]   // C3114  
public ref class R {};  
  
[A(Prop2=123)]   // OK  
public ref class S {};  
```
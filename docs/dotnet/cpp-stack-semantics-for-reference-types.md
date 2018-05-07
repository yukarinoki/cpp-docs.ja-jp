---
title: 参照型の C++ スタック セマンティクス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- reference types, C++ stack semantics for
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b3ed886d1bdeb4972122049854b5d288767aa5b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="c-stack-semantics-for-reference-types"></a>参照型の C++ スタック セマンティクス
Visual C 2005 では、前に、参照型のインスタンスのみ作成でしたを使用して、`new`ガベージにオブジェクトを作成してこの演算子は、ヒープを収集します。 ただし、スタックにネイティブ型のインスタンスの作成に使用する同じ構文を使用して、参照型のインスタンスを作成することができますようになりました。 そのため、使用する必要はありません[ref new、gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)は参照型のオブジェクトを作成します。 オブジェクトがスコープ外になる場合、コンパイラはこのオブジェクトのデストラクターを呼び出します。  
  
## <a name="remarks"></a>コメント  
 コンパイラによって、ガベージ コレクション ヒープでインスタンスが作成される内部的にスタック セマンティクスを使用して、参照型のインスタンスを作成するときに (を使用して`gcnew`)。  
  
 関数のシグネチャまたは戻り値の型には、値で参照型のインスタンスが含まれている場合、関数は (modreq) を持つ特別な処理を必要とすると、メタデータでマークされます。 この特別な処理は現在、Visual C クライアントによって提供されるのみ他の言語はサポートされていませんがかかる関数またはスタック セマンティクスで作成された参照型を使用してデータ。  
  
 使用する理由の 1 つ`gcnew`(動的割り当て) スタックではなくセマンティクスなります型のデストラクターがないかどうか。 また、関数のシグニチャ内のスタック セマンティクスで作成された参照型を使用していない可能性があります、関数が Visual C 以外の言語で使用する場合。  
  
 コンパイラでは、参照型のコピー コンス トラクターは生成されません。 そのため、シグネチャでは値で参照型を使用する関数を定義する場合は、参照型のコピー コンス トラクターを定義する必要があります。 参照型のコピー コンス トラクターは、次の形式の署名:`R(R%){}`です。  
  
 コンパイラでは、参照型の既定の代入演算子は生成されません。 代入演算子を使用すると、スタック セマンティクスを使用してオブジェクトを作成し、スタック セマンティクスを使用して作成された既存のオブジェクトで初期化できます。 参照型の代入演算子は、次の形式の署名:`void operator=( R% ){}`です。  
  
 型のデストラクターは、重要なリソースを解放し、参照型のスタック セマンティクスを使用して場合、は、デストラクターを明示的に呼び出す必要はありません (または呼び出す`delete`)。 参照型のデストラクターの詳細については、次を参照してください。[する方法のデストラクターおよびファイナライザー: を定義およびクラスと構造体を使用 (C + + CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)です。  
  
 コンパイラが生成した代入演算子では、次の項目を追加、通常の標準的な C++ ルールを行います。  
  
-   任意非静的データ メンバーの型は、参照型へのハンドルは shallow (非静的データ メンバーの型がポインターのように扱われます) コピーします。  
  
-   値型を簡易になるという型を持つ任意の非静的データ メンバーがコピーされます。  
  
-   任意の非静的データ メンバーの型が参照型のインスタンスでは、参照型のコピー コンス トラクターの呼び出しを呼び出します。  
  
 コンパイラも用意されています、`%`基になるハンドル型のスタック セマンティクスを使用して作成された参照型のインスタンスに変換する単項演算子です。  
  
 次の参照型では、スタック セマンティクスで使用するため使用できません。  
  
-   [delegate (C++ コンポーネント拡張)](../windows/delegate-cpp-component-extensions.md)  
  
-   [配列](../windows/arrays-cpp-component-extensions.md)  
  
-   <xref:System.String>  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 次のコード サンプルは、スタック セマンティクスで参照型のインスタンスを宣言する方法を示しています。 どのように、代入演算子とコピー コンス トラクターのしくみ、およびスタック セマンティクスを使用して作成された参照型を持つ追跡参照を初期化する方法です。  
  
### <a name="code"></a>コード  
  
```  
// stack_semantics_for_reference_types.cpp  
// compile with: /clr  
ref class R {  
public:  
   int i;  
   R(){}  
  
   // assignment operator  
   void operator=(R% r) {  
      i = r.i;  
   }  
  
   // copy constructor  
   R(R% r) : i(r.i) {}  
};  
  
void Test(R r) {}   // requires copy constructor  
  
int main() {  
   R r1;  
   r1.i = 98;  
  
   R r2(r1);   // requires copy constructor  
   System::Console::WriteLine(r1.i);  
   System::Console::WriteLine(r2.i);  
  
   // use % unary operator to convert instance using stack semantics  
   // to its underlying handle  
   R ^ r3 = %r1;  
   System::Console::WriteLine(r3->i);  
  
   Test(r1);  
  
   R r4;  
   R r5;  
   r5.i = 13;  
   r4 = r5;   // requires a user-defined assignment operator  
   System::Console::WriteLine(r4.i);  
  
   // initialize tracking reference  
   R % r6 = r4;  
   System::Console::WriteLine(r6.i);  
}  
```  
  
### <a name="output"></a>出力  
  
```  
98  
98  
98  
13  
13  
```  
  
## <a name="see-also"></a>関連項目  
 [クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)
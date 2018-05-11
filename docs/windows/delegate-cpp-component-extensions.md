---
title: delegate (C++ コンポーネント拡張) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- delegate_cpp
- delegate
dev_langs:
- C++
helpviewer_keywords:
- delegate keyword [C++]
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73d40bb33509f89273b37f7704cd1922a8d5adc2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="delegate--c-component-extensions"></a>delegate (C++ コンポーネント拡張)
関数ポインターを表す型を宣言します。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 Windows ランタイムと共通言語ランタイムは、デリゲートをサポートします。  
  
### <a name="remarks"></a>コメント  
 `delegate` は状況依存のキーワードです。 詳細については、次を参照してください。[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)です。  
  
 型がある場合、デリゲート、コンパイル時に検出を使用して、`__is_delegate()`型の特徴です。 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)です。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 C + + CX は、次の構文でデリゲートをサポートしています。  
  
### <a name="syntax"></a>構文  
  
```cpp  
access  
delegate  
return-type  
delegate-type-identifier  
(  
[ parameters ]  
)  
  
```  
  
### <a name="parameters"></a>パラメーター  
 *access*  
 (省略可能)可能性があると、デリゲートのアクセシビリティ`public`(既定) または`private`です。 関数プロトタイプを修飾することができますも、`const`または`volatile`キーワード。  
  
 *戻り値の型*  
 関数プロトタイプの戻り値の型。  
  
 *デリゲート型識別子*  
 宣言されたデリゲート型の名前。  
  
 *パラメーター*  
 (省略可能)型および関数のプロトタイプの識別子。  
  
### <a name="remarks"></a>コメント  
 使用して、*デリゲート型識別子*デリゲートと同じプロトタイプを持つイベントを宣言します。 詳細については、次を参照してください。[デリゲート (C + + CX)](../cppcx/delegates-c-cx.md)です。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム  
 共通言語ランタイムは、次の構文でデリゲートをサポートします。  
  
### <a name="syntax"></a>構文  
  
```cpp  
access  
delegate  
function_declaration  
  
```  
  
### <a name="parameters"></a>パラメーター  
 *access*  
 (省略可能)アセンブリの外部でデリゲートのアクセシビリティは、パブリックまたはプライベートにできます。  既定値はプライベートです。  デリゲートは、クラス内、任意のアクセシビリティを持つことができます。  
  
 *function_declaration*  
 デリゲートにバインドできる関数のシグネチャ。 デリゲートの戻り値の型は、任意のマネージ型を指定できます。 相互運用性の理由から、CLS 型、デリゲートの戻り値の型であることをお勧めします。  
  
 バインドされていないデリゲートの最初のパラメーターの定義に*function_declaration*の型にする必要があります、`this`オブジェクトへのポインター。 
  
### <a name="remarks"></a>コメント  
 デリゲートはマルチキャスト:「関数ポインター」は、マネージ クラス内の 1 つまたは複数のメソッドにバインドすることができます。 **委任**キーワードは、特定のメソッド シグネチャを持つマルチキャスト デリゲート型を定義します。  
  
 デリゲートは、静的メソッドなど、値クラスのメソッドにバインドすることもできます。  
  
 デリゲートには、次の特徴があります。  
  
-   継承**system::multicastdelegate**です。  
  
-   2 つの引数を受け取るコンス トラクターがある: マネージ クラスへのポインターまたは**NULL** (静的メソッドへのバインド) の場合と、指定した型のメソッドの完全修飾します。  
  
-   `Invoke` というメソッドを持ち、そのシグネチャはデリゲートの宣言されたシグネチャと一致します。  
  
 デリゲートが呼び出されると、その関数は接続されている順序で呼び出されます。  
  
 デリゲートの戻り値は、その最後のアタッチされたメンバー関数の戻り値です。  
  
 デリゲートは、オーバー ロードすることはできません。  
  
 デリゲートは、バインドまたはバインドされていないことができます。  
  
 バインドされたデリゲートをインスタンス化するとき、最初の引数はオブジェクト参照をでなければいけない。  デリゲートのインスタンス化の 2 番目の引数は、_、マネージ クラス オブジェクトまたはポインターのメソッドのアドレス値型のメソッドにします。   デリゲートのインスタンス化の 2 番目の引数は、完全クラス スコープ構文を使用して、メソッドの名前し、address-of 演算子を適用する必要があります。  
  
 バインドされていないデリゲートをインスタンス化するとき、最初の引数は、マネージ クラス オブジェクトまたは値型のメソッドへのポインターのメソッドのアドレスをいずれかでなければいけない。   引数は、完全クラス スコープ構文を使用して、メソッドの名前、address-of 演算子を適用する必要があります。  
  
 1 つだけのパラメーターは必須で、静的またはグローバル関数へのデリゲートを作成する場合: 関数 (必要に応じて、関数のアドレス)。  
  
 デリゲートの詳細については、次を参照してください。  
  
-   [方法: デリゲートを定義および使用する (C++/CLI)](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)  
  
-   [汎用デリゲート (Visual C++)](../windows/generic-delegates-visual-cpp.md)  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次の例では、宣言、初期化、およびデリゲートを呼び出す方法を示します。  
  
```cpp  
// mcppv2_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare a delegate  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      Console::WriteLine("in func1 {0}", i);  
   }  
  
   void func2(int i) {  
      Console::WriteLine("in func2 {0}", i);  
   }  
  
   static void func3(int i) {  
      Console::WriteLine("in static func3 {0}", i);  
   }  
};  
  
int main () {  
   A ^ a = gcnew A;  
  
   // declare a delegate instance  
   MyDel^ DelInst;  
  
   // test if delegate is initialized  
   if (DelInst)  
      DelInst(7);  
  
   // assigning to delegate  
   DelInst = gcnew MyDel(a, &A::func1);  
  
   // invoke delegate  
   if (DelInst)  
      DelInst(8);  
  
   // add a function  
   DelInst += gcnew MyDel(a, &A::func2);  
  
   DelInst(9);  
  
   // remove a function  
   DelInst -= gcnew MyDel(a, &A::func1);  
  
   // invoke delegate with Invoke  
   DelInst->Invoke(10);  
  
   // make delegate to static function  
   MyDel ^ StaticDelInst = gcnew MyDel(&A::func3);  
   StaticDelInst(11);  
}  
```  
  
 **出力**  
  
```Output  
in func1 8  
  
in func1 9  
  
in func2 9  
  
in func2 10  
  
in static func3 11  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)
---
title: デリゲート (C++ コンポーネント拡張) |Microsoft Docs
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
ms.openlocfilehash: dd35674b61e61eead6118fdcc0aacccbafa6f3b4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649508"
---
# <a name="delegate--c-component-extensions"></a>delegate (C++ コンポーネント拡張)
関数ポインターを表す型を宣言します。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 Windows ランタイムと共通言語ランタイムの両方に、デリゲートをサポートします。  
  
### <a name="remarks"></a>Remarks  
 **委任**は状況依存のキーワードです。 詳細については、次を参照してください。[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)します。  
  
 型がデリゲートの場合は、コンパイル時に検出を使用して、`__is_delegate()`型の特徴です。 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)します。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 C + + CX は、次の構文を持つデリゲートをサポートしています。  
  
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
 (省略可能)代理人のユーザー補助**パブリック**(既定値) または**プライベート**します。 関数プロトタイプを修飾することができますも、 **const**または**揮発性**キーワード。  
  
 *戻り値の型*  
 関数プロトタイプの戻り値の型。  
  
 *デリゲート型の識別子*  
 宣言されたデリゲート型の名前。  
  
 *パラメーター*  
 (省略可能)型および関数プロトタイプの識別子。  
  
### <a name="remarks"></a>Remarks  
 使用して、*デリゲートの型識別子*イベント、デリゲートと同じプロトタイプを宣言します。 詳細については、次を参照してください。[デリゲート (C + + CX)](../cppcx/delegates-c-cx.md)します。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: `/ZW`  
  
## <a name="common-language-runtime"></a>共通言語ランタイム  
 共通言語ランタイムは、次の構文を持つデリゲートをサポートします。  
  
### <a name="syntax"></a>構文  
  
```cpp  
access  
delegate  
function_declaration  
```  
  
### <a name="parameters"></a>パラメーター  
 *access*  
 (省略可能)アセンブリの外部でデリゲートのアクセシビリティは、パブリックまたはプライベートにできます。  既定値はプライベートです。  デリゲートは、クラス内任意のアクセシビリティを持つことができます。  
  
 *function_declaration*  
 デリゲートにバインドできる関数のシグネチャ。 デリゲートの戻り値の型は、任意のマネージ型を指定できます。 相互運用性の理由から、CLS 型、デリゲートの戻り値の型であることをお勧めします。  
  
 最初のパラメーターにバインドされていないデリゲートを定義する*function_declaration*型にする必要があります、**この**オブジェクトへのポインター。 
  
### <a name="remarks"></a>Remarks  
 デリゲートはマルチキャスト:「関数ポインター」は、マネージ クラス内の 1 つまたは複数のメソッドにバインドすることができます。 **委任**キーワードは、特定のメソッド シグネチャを持つマルチキャスト デリゲート型を定義します。  
  
 静的メソッドなど、値クラスのメソッドにデリゲートをバインドすることもできます。  
  
 デリゲートには、次の特徴があります。  
  
-   継承`System::MulticastDelegate`します。  
  
-   2 つの引数を受け取るコンス トラクターがある: マネージ クラスまたは NULL (静的メソッドへのバインド) の場合と指定した型の完全修飾メソッドへのポインター。  
  
-   `Invoke` というメソッドを持ち、そのシグネチャはデリゲートの宣言されたシグネチャと一致します。  
  
 デリゲートが呼び出されたときに、接続されている順序でその関数が呼び出されます。  
  
 デリゲートの戻り値は、その最後の接続されているメンバー関数からの戻り値です。  
  
 デリゲートは、オーバー ロードできません。  
  
 デリゲートをバインドまたはバインド解除することができます。  
  
 バインドされたデリゲートをインスタンス化するとき、最初の引数がオブジェクト参照になります。 デリゲートのインスタンス化の 2 番目の引数は、値型のメソッドに、マネージ クラス オブジェクトまたはポインターのメソッドのアドレスであるか。 デリゲートのインスタンス化の 2 番目の引数は、完全クラス スコープの構文とメソッドの名前し、address-of 演算子を適用する必要があります。  
  
 バインドされていないデリゲートをインスタンス化するとき、最初の引数か、マネージ クラス オブジェクトまたは値型のメソッドへのポインターのメソッドのアドレスになります。 引数は、完全なクラスのスコープの構文とメソッドの名前、address-of 演算子を適用する必要があります。  
  
 グローバルまたは静的関数にデリゲートを作成する場合のみに 1 つのパラメーターが必要です: 関数 (必要に応じて、関数のアドレス)。  
  
 デリゲートの詳細については、次を参照してください。  
  
-   [方法: デリゲートを定義および使用する (C++/CLI)](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)  
  
-   [汎用デリゲート (Visual C++)](../windows/generic-delegates-visual-cpp.md)  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: `/clr`  
  
### <a name="examples"></a>使用例  
  
 次の例では、宣言、初期化、およびデリゲートを起動する方法を示します。  
  
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
  
```Output  
in func1 8  
  
in func1 9  
  
in func2 9  
  
in func2 10  
  
in static func3 11  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)
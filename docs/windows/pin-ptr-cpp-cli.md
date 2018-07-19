---
title: pin_ptr (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- pin_ptr_cpp
- stdcli::language::pin_ptr
- pin_ptr
dev_langs:
- C++
helpviewer_keywords:
- pinning pointers
- pin_ptr keyword [C++]
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: afc99a352e0bde7918cab460293ff23061377551
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880167"
---
# <a name="pinptr-ccli"></a>pin_ptr (C++/CLI)
宣言、*固定ポインター*、共通言語ランタイムでのみ使用されます。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 (この言語機能にはランタイムに適用される特記事項がありません。)  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 (この言語機能はサポートされていません、Windows ランタイムでします。)  
  
## <a name="common-language-runtime"></a>共通言語ランタイム  
 A*固定ポインター*はオブジェクトを妨げる内部ポインターが指すからガベージ コレクトされたヒープに移動します。 つまり、固定ポインターの値は、共通言語ランタイムでは変更されません。 これは、機能は、アドレスは、アンマネージ関数呼び出しの解決時に予期せず変更されないようにするアンマネージ関数に、マネージ クラスのアドレスを渡す際に必要です。  
  
### <a name="syntax"></a>構文  
  
```cpp  
[cli::]pin_ptr<cv_qualifiertype>var = &initializer;  
```  
  
### <a name="parameters"></a>パラメーター  
 *cv_qualifier*  
 `const` または`volatile`修飾子です。 固定ポインターは、既定では、`volatile`です。 固定ポインターを宣言するエラーではなく、余分な`volatile`します。  
  
 *type*  
 `initializer` の型。  
  
 *var*  
 名前、`pin_ptr`変数。  
  
 *initializer*  
 参照型、マネージ配列またはネイティブ ポインターに割り当てることができるその他のオブジェクトの要素のメンバー。  
  
### <a name="remarks"></a>コメント  
 A`pin_ptr`ネイティブ ポインターの機能のスーパー セットを表します。 そのため、何もネイティブ ポインターに割り当てることができることができますに割り当てることも、`pin_ptr`です。 内部ポインターは、比較、ポインターの算術演算などのネイティブ ポインターとして同じ一連の操作を実行する許可します。  
  
 オブジェクトまたは下位のオブジェクトをマネージ クラスのピン留めできます、その場合、共通言語ランタイムが移動しない、ガベージ コレクション中にします。 これの主な用途では、マネージ データへのポインターをアンマネージ関数呼び出しの実パラメーターとして渡します。 コレクション サイクル中に、ランタイムは、固定ポインター用に作成されたメタデータを検査およびを指している項目を移動しません。  
  
 値フィールドをピン留めもオブジェクトをピン留めつまり、またはプリミティブ型のフィールドの値を入力します。 ただし、フィールド宣言ハンドルを追跡することによって (`%`) 固定されません。  
  
 マネージ オブジェクトで定義されている下位のオブジェクトをピン留めすると、オブジェクト全体をピン留めの効果があります。  
  
 固定ポインターを指すように、新しい値を再割り当てする場合、以前のインスタンスを指すと見なされなくピン留めします。  
  
 オブジェクトが固定されている中にのみ、`pin_ptr`それを指しています。 固定ポインターがスコープ外に出るかに設定されているときに、オブジェクトが不要になったピン留め[nullptr](../windows/nullptr-cpp-component-extensions.md)です。 後に、`pin_ptr`ガベージ コレクターによって、ヒープ内がピン留めされたオブジェクトのスコープ外に移動を移動できます。 まだオブジェクトを指す、すべてのネイティブ ポインターは更新されず、および解除のうちの 1 つを参照すると、回復不能な例外が生じる可能性があります。  
  
 オブジェクトを固定ポインターが指していない場合 (すべての固定ポインターがスコープ外になった、他のオブジェクト をポイントに再割り当てされたまたは割り当てられていた[nullptr](../windows/nullptr-cpp-component-extensions.md))、オブジェクトはピン留めすることが保証されます。  
  
 固定ポインターは、参照ハンドル、値型またはボックス化された型のハンドル、マネージ型のメンバーまたはマネージ配列の要素を指定できます。 参照型を指していることはできません。  
  
 アドレスの取得、`pin_ptr`ネイティブ オブジェクトへのポインターが未定義の動作を発生します。  
  
 固定ポインターは、スタックの非静的ローカル変数としてのみ宣言できます。  
  
 固定ポインターとしてを使用できません。  
  
-   関数パラメーター  
  
-   関数の戻り値の型  
  
-   クラスのメンバー  
  
-   キャストの対象の型。  
  
 `pin_ptr` `cli`名前空間。 詳細については、次を参照してください。[プラットフォーム、既定値、および cli 名前空間](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)です。  
  
 内部ポインターの詳細については、次を参照してください。 [interior_ptr (C + + CLI)](../windows/interior-ptr-cpp-cli.md)です。  
  
 固定ポインターの詳細については、次を参照してください。[する方法: ピン ポインターと配列](../windows/how-to-pin-pointers-and-arrays.md)と[する方法: 固定ポインターの宣言と値型](../windows/how-to-declare-pinning-pointers-and-value-types.md)です。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次の例で`pin_ptr`配列の最初の要素の位置を制限します。  
  
```  
// pin_ptr_1.cpp  
// compile with: /clr   
using namespace System;  
#define SIZE 10  
  
#pragma unmanaged  
// native function that initializes an array  
void native_function(int* p) {  
   for(int i = 0 ; i < 10 ; i++)  
    p[i] = i;  
}  
#pragma managed  
  
public ref class A {  
private:  
   array<int>^ arr;   // CLR integer array  
  
public:  
   A() {  
      arr = gcnew array<int>(SIZE);  
   }  
  
   void load() {  
   pin_ptr<int> p = &arr[0];   // pin pointer to first element in arr  
   int* np = p;   // pointer to the first element in arr  
   native_function(np);   // pass pointer to native function  
   }  
  
   int sum() {  
      int total = 0;  
      for (int i = 0 ; i < SIZE ; i++)  
         total += arr[i];  
      return total;  
   }  
};  
  
int main() {  
   A^ a = gcnew A;  
   a->load();   // initialize managed array using the native function  
   Console::WriteLine(a->sum());  
}  
```  
  
 **出力**  
  
```Output  
45  
```  
  
 **例**  
  
 ピンされたポインターを内部ポインターを変換できることと、アドレス演算子の戻り値の型を次の例を示しています (`&`) 内部ポインターは、オペランドが、マネージ ヒープ上にある場合。  
  
```  
// pin_ptr_2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct G {  
   G() : i(1) {}  
   int i;  
};  
  
ref struct H {  
   H() : j(2) {}  
   int j;  
};  
  
int main() {  
   G ^ g = gcnew G;   // g is a whole reference object pointer  
   H ^ h = gcnew H;  
  
   interior_ptr<int> l = &(g->i);   // l is interior pointer  
  
   pin_ptr<int> k = &(h->j);   // k is a pinning interior pointer  
  
   k = l;   // ok  
   Console::WriteLine(*k);  
};  
```  
  
 **出力**  
  
```Output  
1  
```  
  
 **例**  
  
 次の例では、固定ポインターを別の型にキャストできることを示します。  
  
```  
// pin_ptr_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class ManagedType {  
public:  
   int i;  
};  
  
int main() {  
   ManagedType ^mt = gcnew ManagedType;  
   pin_ptr<int> pt = &mt->i;  
   *pt = 8;  
   Console::WriteLine(mt->i);  
  
   char *pc = ( char* ) pt;  
   *pc = 255;  
   Console::WriteLine(mt->i);  
}  
```  
  
 **出力**  
  
```Output  
8  
255  
```
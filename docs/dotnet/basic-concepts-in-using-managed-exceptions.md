---
title: 使用して基本的な概念のマネージ例外 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 255a7d053228b73b2b0eb13f4732e9a7829549ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33114485"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>マネージ例外の使用についての基本概念
このトピックでは、マネージ アプリケーションでの例外処理について説明します。 つまり、と共にコンパイルされるアプリケーション、 **/clr**コンパイラ オプション。  
  
## <a name="in-this-topic"></a>このトピックの内容  
  
-   [/Clr での例外のスロー](#vcconbasicconceptsinusingmanagedexceptionsanchor1)  
  
-   [CLR の拡張機能の Try/catch ブロック](#vcconbasicconceptsinusingmanagedexceptionsanchor2)  
  
## <a name="remarks"></a>コメント  
 コンパイルする場合、 **/clr**オプション、標準と CLR の例外を処理できる[C++ 例外処理](../cpp/cpp-exception-handling.md)と[構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)(SEH)。 CLR 例外は、マネージ型によってスローされる例外です。 [System::exception](https://msdn.microsoft.com/en-us/library/system.exception.aspx)クラスは、CLR の例外を処理するための多くの便利なメソッドを提供し、ユーザー定義の例外クラスの基底クラスとしてはお勧めします。  
  
 インターフェイスから派生した例外の型をキャッチすることはできません **/clr**です。 また、共通言語ランタイムは許可されていませんスタック オーバーフロー例外をキャッチするにはスタック オーバーフロー例外では、プロセスを終了します。  
  
 マネージ コードとアンマネージ アプリケーションでの例外処理の相違の詳細については、次を参照してください。[例外処理の動作で C++ のマネージ拡張の相違](../dotnet/differences-in-exception-handling-behavior-under-clr.md)です。  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a> /Clr での例外のスロー  
 C++ throw 式を拡張して、CLR 型へのハンドルをスローします。 次の例は、カスタムの例外の種類を作成し、し、その型のインスタンスがスローされます。  
  
```  
// clr_exception_handling.cpp  
// compile with: /clr /c  
ref struct MyStruct: public System::Exception {  
public:  
   int i;  
};  
  
void GlobalFunction() {  
   MyStruct^ pMyStruct = gcnew MyStruct;  
   throw pMyStruct;  
}  
```  
  
 値の型は、スローされる前にボックス化する必要があります。  
  
```  
// clr_exception_handling_2.cpp  
// compile with: /clr /c  
value struct MyValueStruct {  
   int i;  
};  
  
void GlobalFunction() {  
   MyValueStruct v = {11};  
   throw (MyValueStruct ^)v;  
}  
```  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a> CLR の拡張機能の Try/catch ブロック  
 同じ**再試行**/**キャッチ**CLR とネイティブの例外の両方をキャッチするためのブロック構造を使用できます。  
  
```  
// clr_exception_handling_3.cpp  
// compile with: /clr  
using namespace System;  
ref struct MyStruct : public Exception {  
public:  
   int i;  
};  
  
struct CMyClass {  
public:  
   double d;  
};  
  
void GlobalFunction() {  
   MyStruct^ pMyStruct = gcnew MyStruct;  
   pMyStruct->i = 11;  
   throw pMyStruct;  
}  
  
void GlobalFunction2() {  
   CMyClass c = {2.0};  
   throw c;  
}  
  
int main() {  
   for ( int i = 1; i >= 0; --i ) {  
      try {  
         if ( i == 1 )  
            GlobalFunction2();  
         if ( i == 0 )  
            GlobalFunction();  
      }  
      catch ( CMyClass& catchC ) {  
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );  
         Console::WriteLine( catchC.d );  
      }  
      catch ( MyStruct^ catchException ) {  
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );  
         Console::WriteLine( catchException->i );  
      }  
   }  
}  
```  
  
### <a name="output"></a>出力  
  
```  
In 'catch(CMyClass& catchC)'  
2  
In 'catch(MyStruct^ catchException)'  
11  
```  
  
### <a name="order-of-unwinding-for-c-objects"></a>C++ オブジェクトのアンワインドの順序  
 スロー元の関数と、処理関数の間で、ランタイム スタックの可能性のあるデストラクターに C++ オブジェクトのアンワインドに発生します。 CLR 型が割り当てられるため、ヒープ上、アンワインドはそれらに適用されません。  
  
 スローされた例外イベントの順序は次のとおりです。  
  
1.  ランタイムにより、適切な catch 句はまたはの場合は、SEH を探してスタックを走査、フィルター、例外をキャッチ、SEH を除く。 Catch 句構文上の順序で最初に検索され、下へ動的に呼び出し履歴。  
  
2.  適切なハンドラーが見つかった後、スタックはその時点までアンワインドではありません。 ローカル オブジェクトの破棄、スタック上の各関数呼び出しについて、_ _finally ブロックは、実行されるほとんどの外側に入れ子にします。  
  
3.  スタックがアンワインドされますが、catch 句が実行されます。  
  
### <a name="catching-unmanaged-types"></a>アンマネージ型をキャッチします。  
 アンマネージ オブジェクトの種類がスローされた場合は、型の例外がスロー ラップ[System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.sehexception.aspx)です。 適切な検索するときに**キャッチ**句は次の 2 つの可能性があります。  
  
-   ネイティブ C++ の型が発生した場合、例外がラップ解除されされ、検出された型と比較します。 この比較では、キャッチされようと通常の方法でネイティブ C++ の型を許可します。  
  
-   ただし場合、**キャッチ**型の句**SEHException**またはその基本クラスのいずれかが最初に検証、句が例外をインターセプトできます。 そのため、いずれかの catch 句の CLR 型の前に、まずネイティブの C++ 型をキャッチするすべての catch 句を配置する必要があります。  
  
 次の点に注意してください。  
  
```  
catch(Object^)  
```  
  
 と、呼び出し  
  
```  
catch(...)  
```  
  
 SEH 例外を含むあらゆるスローされた型をキャッチする両方です。  
  
 アンマネージ型はキャッチされる場合 catch(Object^) によって、スローされたオブジェクトは破棄されません。  
  
 使用することをお勧めスローおよびキャッチする例外を管理しない、ときに、 [/EHsc](../build/reference/eh-exception-handling-model.md)コンパイラ オプションの代わりに **/EHs**または **/EHa**です。  
  
## <a name="see-also"></a>関連項目  
 [例外処理](../windows/exception-handling-cpp-component-extensions.md)   
 [safe_cast](../windows/safe-cast-cpp-component-extensions.md)   
 [例外処理](../cpp/exception-handling-in-visual-cpp.md)
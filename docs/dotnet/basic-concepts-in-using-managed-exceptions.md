---
title: マネージド例外の使用についての基本概念
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
ms.openlocfilehash: 6bc1e9c6d40599ae9a821179dcf56dbb7e21bf10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372528"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>マネージド例外の使用についての基本概念

このトピックでは、マネージ アプリケーションでの例外処理について説明します。 つまり **、/clr**コンパイラ オプションを使用してコンパイルされるアプリケーションです。

## <a name="in-this-topic"></a>このトピックの内容

- [/clr の下で例外をスローする](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [CLR 拡張機能のブロックを試す/キャッチする](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>解説

**/clr**オプションを使用してコンパイルする場合は、CLR 例外を処理できるだけでなく<xref:System.Exception>、標準クラスは CLR 例外を処理するための便利なメソッドを多数提供し、ユーザー定義の例外クラスの基本クラスとして推奨されます。

インターフェイスから派生した例外型をキャッチする場合は **、/clr**ではサポートされていません。 また、共通言語ランタイムでは、スタック オーバーフロー例外をキャッチすることはできません。スタック オーバーフロー例外はプロセスを終了します。

マネージ アプリケーションとアンマネージ アプリケーションでの例外処理の違いの詳細については、「 [C++ マネージ拡張での例外処理動作の違い](../dotnet/differences-in-exception-handling-behavior-under-clr.md)」を参照してください。

## <a name="throwing-exceptions-under-clr"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>/clr の下で例外をスローする

C++ スロー式は CLR 型へのハンドルをスローするように拡張されます。 次の例では、カスタム例外の種類を作成し、その型のインスタンスをスローします。

```cpp
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

値型はスローする前にボックス化する必要があります。

```cpp
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

## <a name="trycatch-blocks-for-clr-extensions"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>CLR 拡張機能のブロックを試す/キャッチする

同じ**try**/**catch**ブロック構造を使用して、CLR 例外とネイティブ例外の両方をキャッチできます。

```cpp
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

アンワインドは、スローする関数と処理関数の間のランタイム スタックに存在する可能性のあるデストラクターを持つ C++ オブジェクトに対して発生します。 CLR 型はヒープに割り当てられるため、アンワインドは適用されません。

スローされた例外のイベントの順序は次のとおりです。

1. ランタイムは、適切な catch 句を探すスタックを走査します。 catch 句は最初に構文順に検索され、次に呼び出し履歴を動的に下にして検索されます。

1. 正しいハンドラが見つかると、スタックはその時点まで巻き戻されます。 スタック上の各関数呼び出しに対して、そのローカルオブジェクトは破壊され、__finallyブロックがネストされた外側から実行されます。

1. スタックが巻き戻されると、catch 句が実行されます。

### <a name="catching-unmanaged-types"></a>アンマネージ型のキャッチ

アンマネージ オブジェクト型がスローされると、型を除いてラップされます<xref:System.Runtime.InteropServices.SEHException>。 適切な**catch**句を検索する場合、2 つの可能性があります。

- ネイティブ C++ 型が検出されると、例外はラップ解除され、検出された型と比較されます。 この比較により、ネイティブ C++ 型を通常の方法でキャッチできます。

- ただし、**型 SEHException**またはその基底クラスのいずれかの**catch**句が最初に調べものとなれば、その句は例外をインターセプトします。 したがって、ネイティブ C++ 型をキャッチするすべての catch 句は、CLR 型の catch 句の前に最初に配置する必要があります。

次の点に注意してください。

```
catch(Object^)
```

and

```
catch(...)
```

SEH 例外を含むスローされた型を両方ともキャッチします。

アンマネージ型が catch(Object^) によってキャッチされた場合、スローされたオブジェクトは破棄されません。

アンマネージ例外をスローまたはキャッチする場合は **、/EHs**または **/EHa**の代わりに[/EHsc](../build/reference/eh-exception-handling-model.md)コンパイラ オプションを使用することをお勧めします。

## <a name="see-also"></a>関連項目

[例外処理](../extensions/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)<br/>
[例外処理](../cpp/exception-handling-in-visual-cpp.md)

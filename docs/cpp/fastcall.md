---
title: _ _fastcall |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __fastcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __fastcall keyword [C++]
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03f286f21f213f5b2a193ccb824ba22b7c7c1f00
ms.sourcegitcommit: 39585672df8874fb5df4e70de97cd7f328fe9880
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2018
---
# <a name="fastcall"></a>__fastcall
**Microsoft 固有の仕様**  
  
 `__fastcall` 呼び出し規約は、可能な場合に、関数への引数をレジスタに渡すことを指定します。 この呼び出し規則は x86 アーキテクチャのみに適用されます。 次の一覧は、この呼び出し規則の実装例を示しています。  
  
|要素|実装|  
|-------------|--------------------|  
|引数を渡す順序|左から右への引数リストで見つかる最初の 2 つの DWORD またはこれより小さい引数は、ECX および EDX レジスタに渡されます。他の引数はすべてスタック上で右から左へ渡されます。|  
|スタック メンテナンスの役割|呼び出された関数によって、スタックから引数がポップされます。|  
|名前装飾規約|アット マーク (\@) は、名前の先頭には、名前に、バイト数 (10 進数)、パラメーターに続くアット リストが付加されたものです。|  
|大文字と小文字の変換規約|大文字小文字は変換されません。|  
  
> [!NOTE]
>  将来のコンパイラ バージョンは、パラメーターを格納するために別のレジスタを使用する可能性があります。  
  
 使用して、 [/Gr](../build/reference/gd-gr-gv-gz-calling-convention.md)コンパイラ オプションでは、各関数をモジュールとしてコンパイルする`__fastcall`関数は、競合する属性を使用して宣言されたか、関数の名前は、しない限り、`main`です。  
  
 `__fastcall` キーワードは、ARM および x64 アーキテクチャを対象とするコンパイラによって受け取られ、無視されます。x64 チップでは、規約により、可能な場合は最初の 4 つの引数がレジスタに渡され、追加の引数はスタック上に渡されます。 詳細については、次を参照してください。[概要の x64 呼び出し規則](../build/overview-of-x64-calling-conventions.md)です。 ARM チップでは、最大で 4 個の整数引数と 8 個の浮動小数点引数をレジスタに渡すことができます。追加の引数はスタック上に渡されます。  
  
 静的でないクラス関数がアウトオブラインで宣言されている場合、アウトオブラインの宣言で呼び出し規則の修飾子を指定する必要はありません。 つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規則が定義の時点で仮定されます。 次のクラス定義があるとします。  
  
```cpp  
struct CMyClass {  
   void __fastcall mymethod();  
};  
```  
  
 ここで、  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 は次の記述と同じです。  
  
```cpp  
void __fastcall CMyClass::mymethod() { return; }  
```  
  
## <a name="example"></a>例  
 次の例では、関数 `DeleteAggrWrapper` にレジスタで引数が渡されます。  
  
```cpp  
// Example of the __fastcall keyword  
#define FASTCALL    __fastcall  
  
void FASTCALL DeleteAggrWrapper(void* pWrapper);  
// Example of the __ fastcall keyword on function pointer  
typedef BOOL (__fastcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)   
 [キーワード](../cpp/keywords-cpp.md)

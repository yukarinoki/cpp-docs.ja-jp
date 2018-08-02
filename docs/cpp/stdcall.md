---
title: _ _stdcall |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __stdcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __stdcall keyword [C++]
ms.assetid: e212594b-1827-4d07-9527-7d412b300df8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f8b845fd147f51e3546f7a11afa0bae6deb5d527
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461466"
---
# <a name="stdcall"></a>__stdcall
**Microsoft 固有の仕様**  
  
 **_ _Stdcall**呼び出し規約は、Win32 API 関数を呼び出すには使用できます。 コンパイラは、呼び出し先がスタックを消去`vararg`関数 **_ _cdecl**します。 この呼び出し規則を使用する関数には、関数プロトタイプが必要です。  
  
## <a name="syntax"></a>構文  
  
```  
return-type __stdcall function-name[(argument-list)]  
```  
  
## <a name="remarks"></a>Remarks  
 次の一覧は、この呼び出し規則の実装例を示しています。  
  
|要素|実装|  
|-------------|--------------------|  
|引数を渡す順序|右から左。|  
|引数渡し規約|ポインターまたは参照型が渡されない場合は、値渡し。|  
|スタック メンテナンスの役割|呼び出された関数が、自分の引数をスタックからポップします。|  
|名前装飾規約|アンダースコア (_) は、名前の前に付けられます。 名前の後に、アットマーク (@) と、引数リストのバイト数 (10 進数) が続きます。 したがって、`int func( int a, double b )` として宣言された関数は次のように修飾されます: `_func@12`|  
|大文字と小文字の変換規約|なし|  
  
 [/Gz](../build/reference/gd-gr-gv-gz-calling-convention.md)コンパイラ オプションを指定します **_ _stdcall**異なる呼び出し規則で明示的に宣言されたすべての関数。  
  
 使用して宣言された関数、 **_ _stdcall**修飾子の戻り値を使用して宣言された関数と同じ方法[_ _cdecl](../cpp/cdecl.md)します。  
  
 ARM と x64 プロセッサでは、 **_ _stdcall**が受け入れられ、無視されます、コンパイラでは、ARM および x64 アーキテクチャでは、慣例により、引数が可能であれば、レジスタで渡され、後続の引数はスタックで渡されます。  
  
 静的でないクラス関数がアウトオブラインで宣言されている場合、アウトオブラインの宣言で呼び出し規則の修飾子を指定する必要はありません。 つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規則が定義の時点で仮定されます。 次のクラス定義の場合、  
  
```cpp  
struct CMyClass {  
   void __stdcall mymethod();  
};  
```  
  
 this  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 は次の記述と同じです。  
  
```cpp  
void __stdcall CMyClass::mymethod() { return; }  
```  
  
## <a name="example"></a>例  
 次の例での使用 **_ _stdcall**すべて`WINAPI`標準呼び出しとして処理される関数の型します。  
  
```cpp  
// Example of the __stdcall keyword  
#define WINAPI __stdcall  
// Example of the __stdcall keyword on function pointer  
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## <a name="see-also"></a>関連項目  
 [引数を渡すと、名前付け規則](../cpp/argument-passing-and-naming-conventions.md)   
 [キーワード](../cpp/keywords-cpp.md)
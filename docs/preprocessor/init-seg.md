---
title: init_seg |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.init_seg
- init_seg_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, init_seg
- init_seg pragma
- data segment initializing [C++]
ms.assetid: 40a5898a-5c85-4aa9-8d73-3d967eb13610
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3be66fc2639253d1bbcfec21f544d5537e084e8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="initseg"></a>init_seg
**C 固有の仕様**  
  
 スタートアップ コードが実行される順序に影響を与えるキーワードまたコード セクションを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma init_seg({ compiler | lib | user | "section-name" [, func-name]} )  
```  
  
## <a name="remarks"></a>コメント  
 用語の意味*セグメント*と*セクション*はこのトピックでは互換性があります。  
  
 グローバルな静的オブジェクトの初期化にはコードの実行を含めることができるため、オブジェクトを構築する時期を定義するキーワードを指定する必要があります。 使用する、特に重要である、 **init_seg**ダイナミック リンク ライブラリ (Dll) にプラグマまたは初期化を必要とするライブラリ。  
  
 オプション、 **init_seg**プラグマは。  
  
 **compiler**  
 Microsoft C ランタイム ライブラリの初期化のために予約されています。 このグループ内のオブジェクトが最初に構築されます。  
  
 **lib**  
 サード パーティの開発元のクラス ライブラリの初期化に使用できます。 としてマークされている後にこのグループ内のオブジェクトが構築される**コンパイラ**がその他の前にします。  
  
 **user**  
 ユーザーが使用できます。 このグループ内のオブジェクトが最後に構築されます。  
  
 *section-name*  
 初期化セクションの明示的な指定を許可します。 ユーザー指定のオブジェクト*セクション名*は暗黙的に構築されていません。 ただし、そのアドレスを配置しているという名前のセクションで*セクション名*です。  
  
 指定したセクション名には、プラグマの後のそのモジュール内で宣言されたグローバル オブジェクトを構築するヘルパー関数へのポインターが格納されます。  
  
 セクションを作成するときに使用しない名前の一覧は、次を参照してください。 [/section](../build/reference/section-specify-section-attributes.md)です。  
  
 *func-name*  
 プログラムの終了時に `atexit` の代わりに呼び出される関数を指定します。 このヘルパー関数を呼び出しても[atexit](../c-runtime-library/reference/atexit.md)グローバル オブジェクトのデストラクターへのポインター。 次の形式のプラグマで関数の識別子を指定した場合、  
  
```  
int __cdecl myexit (void (__cdecl *pf)(void))  
```  
  
 指定した関数が C ランタイム ライブラリの `atexit` の代わりに呼び出されます。 これにより、オブジェクトを破棄する準備ができたときに呼び出す必要のあるデストラクターの一覧を構築できます。  
  
 初期化を遅延する必要がある場合 (たとえば、DLL 内で) セクション名を明示的に指定することもできます。 その後、各静的オブジェクトのコンストラクターを呼び出す必要があります。  
  
 `atexit` の代わりとなる関数は引用符で囲みません。  
  
 それでも、オブジェクトは他の XXX_seg プラグマで定義されたセクションに配置されます。  
  
 モジュール内で宣言されたオブジェクトは C ランタイムで自動的には初期化されません。 これは、自分で行う必要があります。  
  
 既定では、`init_seg` セクションは読み取り専用です。 セクション名が .CRT の場合、属性が読み取り/書き込み可能としてマークされている場合でも、属性はコンパイラによって通知なしで読み取り専用に変更されます。  
  
 指定することはできません**init_seg**翻訳単位内で複数回です。  
  
 オブジェクトにユーザー定義のコンストラクター、つまりコードで明示的に定義されていないコンストラクターがない場合でも、(たとえば v-table ポインターをバインドするために) コンパイラによってコンストラクターが生成される場合があります。  したがって、コードはコンパイラによって生成されたコンストラクターを呼び出す必要があります。  
  
## <a name="example"></a>例  
  
```  
// pragma_directive_init_seg.cpp  
#include <stdio.h>  
#pragma warning(disable : 4075)  
  
typedef void (__cdecl *PF)(void);  
int cxpf = 0;   // number of destructors we need to call  
PF pfx[200];    // pointers to destructors.  
  
int myexit (PF pf) {  
   pfx[cxpf++] = pf;  
   return 0;  
}  
  
struct A {  
   A() { puts("A()"); }  
   ~A() { puts("~A()"); }  
};  
  
// ctor & dtor called by CRT startup code   
// because this is before the pragma init_seg  
A aaaa;   
  
// The order here is important.  
// Section names must be 8 characters or less.  
// The sections with the same name before the $  
// are merged into one section. The order that  
// they are merged is determined by sorting  
// the characters after the $.  
// InitSegStart and InitSegEnd are used to set  
// boundaries so we can find the real functions  
// that we need to call for initialization.  
  
#pragma section(".mine$a", read)  
__declspec(allocate(".mine$a")) const PF InitSegStart = (PF)1;  
  
#pragma section(".mine$z",read)  
__declspec(allocate(".mine$z")) const PF InitSegEnd = (PF)1;  
  
// The comparison for 0 is important.  
// For now, each section is 256 bytes. When they  
// are merged, they are padded with zeros. You  
// can't depend on the section being 256 bytes, but  
// you can depend on it being padded with zeros.  
  
void InitializeObjects () {  
   const PF *x = &InitSegStart;  
   for (++x ; x < &InitSegEnd ; ++x)  
      if (*x) (*x)();  
}  
  
void DestroyObjects () {  
   while (cxpf>0) {  
      --cxpf;  
      (pfx[cxpf])();  
   }  
}  
  
// by default, goes into a read only section  
#pragma init_seg(".mine$m", myexit)  
  
A bbbb;   
A cccc;  
  
int main () {  
   InitializeObjects();  
   DestroyObjects();  
}  
```  
  
```Output  
A()  
A()  
A()  
~A()  
~A()  
~A()  
```  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
---
description: pragmaMicrosoft C/c + + での init_seg ディレクティブの詳細については、こちらを参照してください。
title: init_seg pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.init_seg
- init_seg_CPP
helpviewer_keywords:
- pragma, init_seg
- init_seg pragma
- data segment initializing [C++]
no-loc:
- pragma
ms.openlocfilehash: 77ca6f2454ad18c8adcefcddc4cf1f9c0d4f4532
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713585"
---
# <a name="init_seg-no-locpragma"></a>`init_seg` pragma

**C++ 固有の仕様**

スタートアップ コードが実行される順序に影響を与えるキーワードまたコード セクションを指定します。

## <a name="syntax"></a>構文

> **`#pragma init_seg(`** { **`compiler`** | **`lib`** | **`user`** |"*section-name*" [ **`,`** *func-name* ]} **`)`**

## <a name="remarks"></a>解説

この記事では、 *セグメント* と *セクション* という用語は同じ意味を持ちます。

グローバルな静的オブジェクトの初期化にはコードが必要になることがあるため、オブジェクトを構築するタイミングを指定する必要があります。 特に、 **`init_seg`** pragma 動的リンクライブラリ (dll) の、または初期化が必要なライブラリでを使用することが重要です。

のオプションは **`init_seg`** pragma 次のとおりです。

**`compiler`**\
Microsoft C ランタイム ライブラリの初期化のために予約されています。 このグループ内のオブジェクトが最初に構築されます。

**`lib`**\
サード パーティの開発元のクラス ライブラリの初期化に使用できます。 このグループのオブジェクトは、としてマークされているオブジェクトの後、他のオブジェクトの前に構築され **`compiler`** ます。

**`user`**\
ユーザーが使用できます。 このグループ内のオブジェクトが最後に構築されます。

*セクション-名前*\
初期化セクションの明示的な指定を許可します。 ユーザー指定の *セクション名* のオブジェクトは暗黙的に構築されません。 ただし、これらのアドレスは、セクション *名* によって名前が付けられたセクションに配置されます。

指定した *セクション名* には、そのモジュール内のの後に宣言されたグローバルオブジェクトを構築するヘルパー関数へのポインターが含まれ pragma ます。

セクションを作成するときに使用しない名前の一覧については、「」を参照してください [`/SECTION`](../build/reference/section-specify-section-attributes.md) 。

*func-名前*\
プログラムの終了時に `atexit` の代わりに呼び出される関数を指定します。 また、このヘルパー関数 [`atexit`](../c-runtime-library/reference/atexit.md) は、グローバルオブジェクトのデストラクターへのポインターを使用してを呼び出します。 の形式で関数識別子を指定する場合は pragma 、

```cpp
int __cdecl myexit (void (__cdecl *pf)(void))
```

指定した関数が C ランタイム ライブラリの `atexit` の代わりに呼び出されます。 これにより、オブジェクトを破棄する準備ができたときに呼び出すデストラクターのリストを作成できます。

初期化を遅延する必要がある場合 (たとえば、DLL 内で) セクション名を明示的に指定することもできます。 コードでは、各静的オブジェクトのコンストラクターを呼び出す必要があります。

`atexit` の代わりとなる関数は引用符で囲みません。

オブジェクトは、他のディレクティブによって定義されたセクションに配置され `XXX_seg` pragma ます。

モジュールで宣言されているオブジェクトは、C ランタイムによって自動的に初期化されるわけではありません。 コードで初期化を行う必要があります。

既定では、`init_seg` セクションは読み取り専用です。 セクション名がの場合 `.CRT` 、コンパイラは、読み取り、書き込みとしてマークされている場合でも、属性を自動的に読み取り専用に変更します。

1つの **`init_seg`** 翻訳単位で複数回指定することはできません。

オブジェクトが、コードで明示的に定義されたユーザー定義のコンストラクターを持っていない場合でも、コンパイラが生成することがあります。 たとえば、v テーブルポインターをバインドするために1つを作成できます。 必要に応じて、コードはコンパイラによって生成されたコンストラクターを呼び出します。

## <a name="example"></a>例

```cpp
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

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)

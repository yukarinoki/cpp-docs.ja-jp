---
description: '詳細情報: pack プラグマ'
title: pack プラグマ
ms.date: 07/22/2020
f1_keywords:
- pack_CPP
- vc-pragma.pack
helpviewer_keywords:
- pragmas, pack
- pack pragma
ms.assetid: e4209cbb-5437-4b53-b3fe-ac264501d404
ms.openlocfilehash: d4e4cbba13efabd148fdd61f59eebb15c56b1c41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333192"
---
# <a name="pack-pragma"></a>pack プラグマ

構造体、共用体、およびクラスメンバーのパッキングアラインメントを指定します。

## <a name="syntax"></a>構文

> **`#pragma pack( show )`**\
> **`#pragma pack( push`** [ **`,`** *`identifier`* ] [ **`,`** *`n`* ] **`)`**\
> **`#pragma pack( pop`** [ **`,`** { *`identifier`* | *`n`* } ] **`)`**\
> **`#pragma pack(`** [ *`n`* ] **`)`**

### <a name="parameters"></a>パラメーター

**`show`**\
Optionalパッキングアラインメントの現在のバイト値を表示します。 値は警告メッセージによって表示されます。

**`push`**\
Optional現在のパッキングアラインメント値を内部コンパイラスタックにプッシュし、現在のパッキングアラインメント値を *n* に設定します。 *N* が指定されていない場合、現在のパッキングアラインメント値がプッシュされます。

**`pop`**\
Optional内部コンパイラスタックの先頭からレコードを削除します。 *N* がで指定されていない場合 **`pop`** 、スタックの一番上にある結果のレコードに関連付けられているパッキング値が新しいパッキングアラインメント値になります。 *N* が指定されている場合、たとえば、n が `#pragma pack(pop, 16)` 新しいパッキングアラインメント値になります。  たとえば、を使用して pop を使用した場合、スタック上のすべてのレコードが、の *`identifier`* `#pragma pack(pop, r1)` レコードが見つかるまでポップされ *`identifier`* ます。 そのレコードがポップされ、スタックの一番上にあるレコードに関連付けられたパッキング値が新しいパッキングアラインメント値になります。 スタック上のどのレコードにも存在しないを使用して pop を使用すると *`identifier`* 、 **`pop`** は無視されます。

ステートメントは、の後にを付けた `#pragma pack (pop, r1, 2)` ものと同じです `#pragma pack (pop, r1)` `#pragma pack(2)` 。

*`identifier`*\
Optionalと共に使用すると **`push`** 、内部コンパイラスタックのレコードに名前を割り当てます。 と共に使用すると **`pop`** 、が削除されるまで、レコードは内部スタックからポップされ *`identifier`* ます。 が *`identifier`* 内部スタックで見つからない場合は、何もポップされません。

*`n`*\
Optionalパッキングに使用する値をバイト単位で指定します。 コンパイラオプションが [`/Zp`](../build/reference/zp-struct-member-alignment.md) モジュールに対して設定されていない場合、の既定値 *`n`* は8になります。 有効値は 1、2、4、8、および 16 です。 メンバーのアラインメントは、の倍数 *`n`* またはメンバーのサイズの倍数のいずれか小さい方の境界上にあります。

## <a name="remarks"></a>解説

クラスを *パック* するには、そのメンバーをメモリ内で相互に直接配置します。 一部またはすべてのメンバーを、ターゲットアーキテクチャの既定の配置よりも小さい境界に配置できることを意味します。 **`pack`** データ宣言レベルでコントロールを提供します。 これは [`/Zp`](../build/reference/zp-struct-member-alignment.md) 、モジュールレベルの制御のみを提供するコンパイラオプションとは異なります。 **パッケージ** は、 **`struct`** **`union`** **`class`** プラグマが表示された後、最初の、、または宣言で有効になります。 **`pack`** 定義には影響しません。 **`pack`** 引数を指定せずにを呼び出すと *`n`* 、コンパイラオプションで設定された値に設定され **`/Zp`** ます。 コンパイラオプションが設定されていない場合、x86、ARM、および ARM64 の既定値は8です。 既定値は、x64 ネイティブの場合は16です。

構造体のアラインメントを変更した場合、メモリ内で使用されている領域が使用できなくなる可能性があります。 ただし、不均等なアクセスでは、パフォーマンスが低下したり、ハードウェアによって生成された例外が発生したりする可能性があります。 この例外動作は、を使用して変更でき [`SetErrorMode`](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) ます。

配置を変更する方法の詳細については、次の記事を参照してください。

- [`alignof`](../cpp/alignof-operator.md)

- [`align`](../cpp/align-cpp.md)

- [`__unaligned`](../cpp/unaligned.md)

- [構造体のアラインメントの例](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 固有)

   > [!WARNING]
   > Visual Studio 2015 以降では、と **`alignas`** は異なり、コンパイラ間で移植可能な標準および演算子を使用でき **`alignof`** **`__alignof`** **`__declspec( align )`** ます。 C++ 標準ではパッキングが解決されないため、 **`pack`** (または他のコンパイラの対応する拡張機能) を使用して、ターゲットアーキテクチャのワードサイズより小さいアラインメントを指定する必要があります。

## <a name="examples"></a>例

次のサンプルは、プラグマを使用して構造体のアラインメントを変更する方法を示して **`pack`** います。

```cpp
// pragma_directives_pack.cpp
#include <stddef.h>
#include <stdio.h>

struct S {
   int i;   // size 4
   short j;   // size 2
   double k;   // size 8
};

#pragma pack(2)
struct T {
   int i;
   short j;
   double k;
};

int main() {
   printf("%zu ", offsetof(S, i));
   printf("%zu ", offsetof(S, j));
   printf("%zu\n", offsetof(S, k));

   printf("%zu ", offsetof(T, i));
   printf("%zu ", offsetof(T, j));
   printf("%zu\n", offsetof(T, k));
}
```

```Output
0 4 8
0 4 6
```

次の例では、 *プッシュ*、 *ポップ*、および *表示* の各構文を使用する方法を示します。

```cpp
// pragma_directives_pack_2.cpp
// compile with: /W1 /c
#pragma pack()   // n defaults to 8; equivalent to /Zp8
#pragma pack(show)   // C4810
#pragma pack(4)   // n = 4
#pragma pack(show)   // C4810
#pragma pack(push, r1, 16)   // n = 16, pushed to stack
#pragma pack(show)   // C4810

// pop to the identifier and then set
// the value of the current packing alignment:
#pragma pack(pop, r1, 2)   // n = 2 , stack popped
#pragma pack(show)   // C4810
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

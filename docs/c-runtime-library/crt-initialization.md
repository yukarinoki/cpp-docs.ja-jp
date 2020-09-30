---
title: CRT の初期化
description: CRT がネイティブコードでグローバル状態を初期化する方法について説明します。
ms.topic: conceptual
ms.date: 11/04/2016
helpviewer_keywords:
- CRT initialization [C++]
ms.assetid: e7979813-1856-4848-9639-f29c86b74ad7
ms.openlocfilehash: 25f1e2a7e5b7d91c729bb45bd79ba9a8720cead1
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "91589771"
---
# <a name="crt-initialization"></a>CRT の初期化

このトピックでは、CRT がネイティブコードでグローバル状態を初期化する方法について説明します。

既定では、リンカーには、独自のスタートアップ コードを提供する CRT ライブラリが含まれています。 このスタートアップ コードは、CRT ライブラリを初期化し、グローバル初期化子を呼び出し、コンソール アプリケーション用のユーザー指定の `main` 関数を呼び出します。

## <a name="initializing-a-global-object"></a>グローバル オブジェクトの初期化

次のコードがあるとします。

```
int func(void)
{
    return 3;
}

int gi = func();

int main()
{
    return gi;
}
```

C と C++ の標準に従えば、`func()` は `main()` を実行する前に呼び出す必要があります。 では、呼び出し元は何でしょうか。

呼び出し元を特定する方法の1つとして、にブレークポイントを設定し、 `func()` アプリケーションをデバッグして、スタックを調べる方法があります。 これは Visual Studio に CRT ソース コードが含まれているから可能なことです。

スタック上の関数を参照すると、CRT が関数ポインターのリストを呼び出していることがわかります。 これらの関数は `func()` 、またはクラスインスタンスのコンストラクターに似ています。

CRT は、Microsoft C++ コンパイラから関数ポインターのリストを取得します。 コンパイラは、グローバル初期化子を認識すると、セクションに動的な初期化子を生成します。ここで、 `.CRT$XCU` `CRT` はセクション名、 `XCU` はグループ名です。 動的初期化子の一覧を取得するには、コマンド **dumpbin/all**を実行し、セクションを検索し `.CRT$XCU` ます。 これは、メイン .cpp が C ファイルではなく C++ ファイルとしてコンパイルされる場合に適用されます。 次の例のようになります。

```
SECTION HEADER #6
.CRT$XCU name
       0 physical address
       0 virtual address
       4 size of raw data
     1F2 file pointer to raw data (000001F2 to 000001F5)
     1F6 file pointer to relocation table
       0 file pointer to line numbers
       1 number of relocations
       0 number of line numbers
40300040 flags
         Initialized Data
         4 byte align
         Read Only

RAW DATA #6
  00000000: 00 00 00 00                                      ....

RELOCATIONS #6
                                               Symbol    Symbol
Offset    Type              Applied To         Index     Name
--------  ----------------  -----------------  --------  -------
00000000  DIR32             00000000           C         ??__Egi@@YAXXZ (void __cdecl `dynamic initializer for 'gi''(void))
```

CRT では、2 つのポインターを定義します。

- 『`.CRT$XCA`』の「`__xc_a`」

- 『`.CRT$XCZ`』の「`__xc_z`」

以外のどのグループにも、およびを除く他のシンボルが定義されてい `__xc_a` `__xc_z` ます。

リンカーがさまざまな `.CRT` グループを読み取るとき、グループを 1 つのセクションに結合し、アルファベット順に並べ替えます。 つまり、ユーザー定義のグローバル初期化子 (Microsoft C++ コンパイラでは `.CRT$XCU` 内にあります) は常に `.CRT$XCA` の後にあり、`.CRT$XCZ` の前にあります。

セクションは、次の例のようになります。

```
.CRT$XCA
            __xc_a
.CRT$XCU
            Pointer to Global Initializer 1
            Pointer to Global Initializer 2
.CRT$XCZ
            __xc_z
```

そのため、CRT ライブラリは、との両方を使用し `__xc_a` て、 `__xc_z` グローバル初期化子リストの開始と終了を決定します。これは、イメージが読み込まれた後にメモリにレイアウトされるためです。

## <a name="see-also"></a>関連項目

[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)

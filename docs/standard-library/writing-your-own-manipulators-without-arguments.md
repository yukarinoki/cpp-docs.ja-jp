---
description: '詳細情報: 引数を指定せずに独自のマニピュレーターを作成する'
title: 引数を使用しない独自マニピュレーターの作成
ms.date: 11/04/2016
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
ms.openlocfilehash: 593db0a3dacb54c94cc865ebc20b1e1b39d2c208
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187755"
---
# <a name="writing-your-own-manipulators-without-arguments"></a>引数を使用しない独自マニピュレーターの作成

引数を使用しないマニピュレーターを作成するには、クラスを派生させる必要も、複雑なマクロを使う必要もありません。 プリンターで \<ESC> [太字モードにするには、ペアが必要です。 このペアは、次のようにして、ストリームに直接挿入できます。

```cpp
cout << "regular " << '\033' << '[' << "boldface" << endl;
```

または、次のように `bold` マニピュレーターを定義して、文字を挿入することもできます。

```cpp
ostream& bold(ostream& os) {
    return os << '\033' << '[';
}
cout << "regular " << bold << "boldface" << endl;
```

グローバルに定義された `bold` 関数は、引数として `ostream` の参照をとり、`ostream` の参照を返します。 この関数は、プライベート クラス要素にアクセスする必要がないため、メンバー関数でもフレンド関数でもありません。 `bold` 関数は、ストリームの `<<` 演算子がその型の関数を受け付けるようにオーバーロードされているため、次のような宣言を使用してストリームに接続します。

```cpp
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))
{
    // call ios_base manipulator
    (*_Pfn)(*(ios_base *)this);

    return (*this);
}
```

この機能を使うと、その他のオーバーロードされた演算子を拡張することができます。 この場合、`bold` がストリームに文字を挿入することは付随的な事柄です。 この関数は、関数がストリームに挿入された時点で呼び出されます。これは、必ずしも隣接する文字が印刷される時点ではありません。 したがって、ストリームのバッファリングの影響で、印刷が遅れる可能性があります。

## <a name="see-also"></a>関連項目

[出力ストリーム](../standard-library/output-streams.md)

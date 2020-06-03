---
title: 名前の装飾
ms.date: 04/22/2019
helpviewer_keywords:
- name decoration [C++]
- names [C++], decorated
- decorated names, calling conventions
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
ms.openlocfilehash: cc00c971eac2a089ccec5bd9eab594bdf4e8348e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173518"
---
# <a name="name-decoration"></a>名前の装飾

名前の装飾は、通常は C++ の名前付け規則を指しますが、C の場合でもよく適用されます。 既定では、C++ では関数名、パラメーター、および戻り値の型を使用して、関数のリンカー名が作成されます。 次の関数の宣言について考えてみます。

`void CALLTYPE test(void);`

次の表は、さまざまな呼び出し規約のリンカー名を示します。

|呼び出し規約|`extern "C"` または `.c` ファイル|`.cpp`、`.cxx` または `/TP`|
|------------------------|---------------------------|------------------------|
|C の名前付け規則 (`__cdecl`)|`_test`|`?test@@ZAXXZ`|
|高速呼び出しの名前付け規則 (`__fastcall`)|`@test@0`|`?test@@YIXXZ`|
|標準呼び出しの名前付け規則 (`__stdcall`)|`_test@0`|`?test@@YGXXZ`|
|ベクター呼び出しの名前付け規則 (`__vectorcall`)|`test@@0`|`?test@@YQXXZ`|

からC++C 関数を呼び出すには、`extern "C"` を使用します。 `extern "C"` は、非クラスC++関数に対して C 名前付け規則を強制的に使用します。 コンパイラスイッチ **/tc**または **/tp**に注意してください。これは、ファイル名の拡張子を無視し、ファイルをC++C またはとしてコンパイルするようにコンパイラに指示します。 これらのオプションを使用すると、予期しないリンカー名が発生する可能性があります。

関数プロトタイプのパラメーターが一致していないと、このエラーが発生します。 名前の装飾では、関数のパラメーターを最終の装飾関数名に組み込みます。 関数宣言内のパラメーターの型と一致しない関数を呼び出すと、LNK2001 が発生することがあります。

現在、コンパイラベンダー間でC++の名前付け、または異なるバージョンのコンパイラ間での名前付けの標準はありません。 他のコンパイラによってコンパイルされたオブジェクトファイルをリンクすると、同じ名前付けスキームが生成されず、外部の未解決の原因になる可能性があります。

## <a name="see-also"></a>参照

[リンカー ツール エラー LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md)

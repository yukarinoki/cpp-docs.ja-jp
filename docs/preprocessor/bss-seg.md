---
title: bss_seg
ms.date: 10/22/2018
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
ms.openlocfilehash: 489ced11bb6024fdf9818872c07ab7feebfeabf3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566310"
---
# <a name="bssseg"></a>bss_seg

初期化されていない変数が格納される .obj ファイル内のセグメントを指定します。

## <a name="syntax"></a>構文

```
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )
```

### <a name="parameters"></a>パラメーター

**push**<br/>
(省略可能)内部コンパイラ スタックには、レコードを設定します。 A *pu*sh * ことができますが、*識別子*と*セグメント名*します。

**pop**<br/>
(省略可能)内部コンパイラ スタックの上部からレコードを削除します。

*identifier*<br/>
(省略可能)使用すると**プッシュ**、内部コンパイラ スタックのレコードに名前を割り当てます。 *識別子*により、複数のレコードを 1 つのポップを**pop**コマンド。 使用すると**pop**、ディレクティブのポップ レコードまで内部スタックからポップ*識別子*が削除された場合*識別子*が見つからない内部スタックではありませんポップされます。

*「セグメント名」*<br/>
(省略可能)セグメントの名前。 使用すると**pop**、スタックがポップされ、*セグメント名*がアクティブなセグメント名になります。

*「セグメント クラス」*<br/>
(省略可能)C++ との互換性をバージョン 2.0 より前に含まれています。 これは無視されます。

## <a name="remarks"></a>Remarks

.Obj ファイルを表示できる、 [dumpbin](../build/reference/dumpbin-command-line.md)アプリケーション。 初期化されていないデータの .obj ファイルの既定セグメントは、.bss です。 場合によっては使用**bss_seg**高速化できますの読み込み時間の 1 つのセクションに初期化されていないデータをグループ化します。

**bss_seg**パラメーターなしで、セグメントを .bss にリセットします。

データを使用して割り当て、 **bss_seg**プラグマがその場所に関する情報を保持していません。

初期化されたデータのセクションを指定することもできます ([data_seg](../preprocessor/data-seg.md))、関数 ([code_seg](../preprocessor/code-seg.md))、および const 変数 ([const_seg](../preprocessor/const-seg.md))。

参照してください[/section](../build/reference/section-specify-section-attributes.md)に対して一連の名前のセクションを作成するときに使用する必要があります。

## <a name="example"></a>例

```cpp
// pragma_directive_bss_seg.cpp
int i;                     // stored in .bss
#pragma bss_seg(".my_data1")
int j;                     // stored in .my_data1

#pragma bss_seg(push, stack1, ".my_data2")
int l;                     // stored in .my_data2

#pragma bss_seg(pop, stack1)   // pop stack1 from stack
int m;                     // stored in .my_data1

int main() {
}
```

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

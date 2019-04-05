---
title: section
ms.date: 11/04/2016
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
ms.openlocfilehash: 41479d7d8767438d0e59fbe6beb7e435459dcb1b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023244"
---
# <a name="section"></a>section

.obj ファイルにセクションを作成します。

## <a name="syntax"></a>構文

```
#pragma section( "section-name" [, attributes] )
```

## <a name="remarks"></a>Remarks

用語の意味*セグメント*と*セクション*はこのトピックでは互換性があります。

セクションを定義すると、そのセクションはそれ以降のコンパイルで有効になります。 ただし、使用する必要があります[__declspec(allocate)](../cpp/allocate.md)セクションに何も配置されますか。

*セクション名*セクションの名前となる必須パラメーターです。 標準セクション名と競合する名前は付けられません。 参照してください[/section](../build/reference/section-specify-section-attributes.md)に対して一連の名前のセクションを作成するときに使用する必要があります。

*属性*属性から成る 1 つまたは複数コンマで区切られた、セクションに割り当てる省略可能なパラメーターです。 考えられる*属性*は。

|属性|説明|
|-|-|
|**読み取り**|データの読み取り操作を有効にします。|
|**書き込み**|データの書き込み操作を有効にします。|
|**実行 (execute)**|コードを実行できるようにします。|
|**shared**|イメージを読み込んだすべてのプロセス間でセクションを共有します。|
|**nopage**|セクションをページング不可にします。Win32 デバイス ドライバー用です。|
|**nocache**|セクションをキャッシュ不可にします。Win32 デバイス ドライバー用です。|
|**discard**|セクションを破棄可能にします。Win32 デバイス ドライバー用です。|
|**remove**|セクションをメモリ非常駐; としてマークします。仮想デバイス ドライバー (V*x*D) のみです。|

属性を指定しない場合、セクションには読み取り属性と書き込み属性が設定されます。

## <a name="example"></a>例

次の例では、最初の命令でセクションとその属性を指定しています。 `j` を使用して宣言していないので、整数 `mysec` は `__declspec(allocate)` に追加されません。`j` はデータ セクションに配置されます。 整数 `i` は、その `mysec` ストレージ クラス属性の結果として `__declspec(allocate)` に追加されます。

```cpp
// pragma_section.cpp
#pragma section("mysec",read,write)
int j = 0;

__declspec(allocate("mysec"))
int i = 0;

int main(){}
```

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
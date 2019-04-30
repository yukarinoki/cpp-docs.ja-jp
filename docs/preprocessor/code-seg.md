---
title: code_seg
ms.date: 11/04/2016
f1_keywords:
- code_seg_CPP
- vc-pragma.code_seg
helpviewer_keywords:
- pragmas, code_seg
- code_seg pragma
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
ms.openlocfilehash: e566fb01bf70b343b75254a10466bdda2bc7ce1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403504"
---
# <a name="codeseg"></a>code_seg
関数が格納される .obj ファイル内のテキスト セグメントを指定します。

## <a name="syntax"></a>構文

```
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )
```

### <a name="parameters"></a>パラメーター

**push**<br/>
(省略可能)内部コンパイラ スタックには、レコードを設定します。 A**プッシュ**できますが、*識別子*と*セグメント名*します。

**pop**<br/>
(省略可能)内部コンパイラ スタックの上部からレコードを削除します。

*identifier*<br/>
(省略可能)使用すると**プッシュ**、内部コンパイラ スタックのレコードに名前を割り当てます。 使用すると**pop**、レコードまで内部スタックからポップ*識別子*が削除された場合*識別子*は内部のスタックに何もポップされます。

*識別子*により、複数のレコードを 1 つだけでポップできます**pop**コマンド。

"*segment-name*"<br/>
(省略可能)セグメントの名前。 使用すると**pop**、スタックがポップされ、*セグメント名*アクティブなテキスト セグメント名になります。

"*segment-class*"<br/>
(省略可能)バージョン 2.0 より前のバージョンの C との互換性が無視されます。

## <a name="remarks"></a>Remarks

**Code_seg**プラグマ ディレクティブは、インスタンス化されたテンプレートは、生成されたオブジェクト コードも、コンパイラによって暗黙的に生成されたコードの配置を制御しません-たとえば、特殊なメンバー関数。 使用することをお勧め、 [__declspec(code_seg(...)](../cpp/code-seg-declspec.md)属性の代わりに使用するすべてのオブジェクト コードの配置を制御します。 コンパイラによって生成されたコードの格納場所も制御できるためです。

A*セグメント*.obj ファイルは名前付きのユニットとしてメモリに読み込まれるデータのブロック。 A*テキスト セグメント*は実行可能コードを含むセグメントです。 この記事で、条項*セグメント*と*セクション*は同義です。

**Code_seg**プラグマ ディレクティブを指定すると、翻訳単位からの後続のオブジェクトのすべてのコードをという名前のテキスト セグメントに配置*セグメント名*します。 既定では、.obj ファイル内の関数に使用されるテキスト セグメントには .text という名前が付けられます。

A **code_seg**プラグマ ディレクティブ パラメーターを指定せず、後続のオブジェクト コードのテキスト セグメント名を .text にリセットします。

使用することができます、 [DUMPBIN します。EXE](../build/reference/dumpbin-command-line.md) .obj ファイルを表示するアプリケーション。 各サポートされているターゲット アーキテクチャの DUMPBIN のバージョンは Visual Studio に含まれています。

## <a name="example"></a>例

この例は、使用する方法を示します、 **code_seg**プラグマ ディレクティブをオブジェクト コードの格納場所を制御します。

```cpp
// pragma_directive_code_seg.cpp
void func1() {                  // stored in .text
}

#pragma code_seg(".my_data1")
void func2() {                  // stored in my_data1
}

#pragma code_seg(push, r1, ".my_data2")
void func3() {                  // stored in my_data2
}

#pragma code_seg(pop, r1)      // stored in my_data1
void func4() {
}

int main() {
}
```

セクションを作成する使わないで名の一覧は、次を参照してください。 [/section](../build/reference/section-specify-section-attributes.md)します。

初期化されたデータのセクションを指定することもできます ([data_seg](../preprocessor/data-seg.md))、初期化されていないデータ ([bss_seg](../preprocessor/bss-seg.md))、および const 変数 ([const_seg](../preprocessor/const-seg.md))。

## <a name="see-also"></a>関連項目

[code_seg (__declspec)](../cpp/code-seg-declspec.md)<br/>
[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
---
title: 記述ブロック
description: NMAKE は、注釈ブロックを使用して、メイクファイル内のターゲット、依存関係、およびコマンドを関連付けます。
ms.date: 10/29/2019
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
ms.openlocfilehash: e4e80b59d3d30b3b34c55b40d337ef5c078e6404
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322258"
---
# <a name="description-blocks"></a>記述ブロック

記述ブロックは、メイクファイルの中核を形成します。 作成する*ターゲット*またはファイル、およびターゲットの作成に必要なファイル 、およびそれらの*依存関係*について説明します。 記述ブロックには、 依存関係からターゲットを作成する方法を記述する*コマンド*が含まれる場合があります。 説明ブロックは依存関係行であり、オプションでコマンド ブロックが続きます。

```makefile
targets... : dependents...
    commands...
```

## <a name="dependency-lines"></a>依存明細行

*依存関係行*は、1 つ以上のターゲットとゼロ個以上の従属を指定します。 ターゲットが存在しない場合、または依存するタイムスタンプよりも前のタイムスタンプがある場合、NMAKE はコマンド ブロック内のコマンドを実行します。 NMAKE は、ターゲットが[疑似ターゲット](pseudotargets.md)である場合にもコマンド ブロックを実行します。 依存関係行の例を次に示します。

```makefile
hi_bye.exe : hello.obj goodbye.obj helper.lib
```

この依存関係行では、`hi_bye.exe`ターゲットです。 その依存関係は`hello.obj`、 `goodbye.obj`、 `helper.lib`、および です。 `hello.obj`依存関係行は、 、 `goodbye.obj`、または`helper.lib`が変更された場合に常にターゲットを`hi_bye.exe`作成するように NMAKE に指示します。

ターゲットは、行の先頭になければなりません。 スペースやタブでインデントすることはできません。 ターゲットと依存オブジェクト`:`を区切るには、コロン ( ) を使用します。 ターゲット、コロン区切り (`:`) 、および依存変数の間には、スペースまたはタブを使用できます。 依存関係行を分割するには、ターゲットまたは依存の後`\`に円記号 ( ) を使用します。

コマンド ブロックを実行する前に、NMAKE はすべての依存関係と適用可能な推論規則をスキャンして *、依存関係ツリー*を構築します。 依存関係ツリーは、ターゲットを完全に更新するために必要なステップを指定します。 NMAKE は、依存が依存する依存関係の一覧のターゲットであるかどうかを再帰的にチェックします。 依存関係ツリーを構築すると、NMAKE はタイム スタンプをチェックします。 ツリー内の依存がターゲットより新しい場合、NMAKE はターゲットをビルドします。

## <a name="targets"></a><a name="targets"></a>ターゲット

依存関係行のターゲット セクションでは、1 つ以上のターゲットを指定します。 ターゲットには、有効なファイル名、ディレクトリ名、または[疑似ターゲット](pseudotargets.md)を指定できます。 1 つ以上のスペースまたはタブを使用して、複数のターゲットを分離します。 ターゲットは大文字と小文字を区別しません。 パスはファイル名で許可されています。 ターゲットとそのパスは 256 文字を超えることはできません。 コロンの前のターゲットが 1 文字の場合は、区切りスペースを使用します。 それ以外の場合、NMAKE は文字とコロンの組み合わせをドライブ指定子として解釈します。

### <a name="multiple-targets"></a><a name="multiple-targets"></a>複数のターゲット

NMAKE では、1 つの依存関係で、それぞれが個別の記述ブロックで指定された場合と同様に複数のターゲットが評価されます。

たとえば、次のルールを使用します。

```makefile
bounce.exe leap.exe : jump.obj
   echo Building...
```

は次のように評価されます。

```makefile
bounce.exe : jump.obj
   echo Building...

leap.exe : jump.obj
   echo Building...
```

### <a name="cumulative-dependencies"></a><a name="cumulative-dependencies"></a>累積依存関係

ターゲットが繰り返される場合、依存関係は記述ブロック内で累積されます。

たとえば、この一連のルールは、

```makefile
bounce.exe : jump.obj
bounce.exe : up.obj
   echo Building bounce.exe...
```

は次のように評価されます。

```makefile
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

1 つの記述ブロック内の複数の依存関係行に複数のターゲットがある場合、NMAKE は、それぞれが別個の記述ブロックで指定されたかのように評価します。 ただし、最後の依存関係行のターゲットのみがコマンド ブロックを使用します。 NMAKE は、他のターゲットに対して推論規則を使用しようとします。

たとえば、この一連のルールは、

```makefile
leap.exe bounce.exe : jump.obj
bounce.exe climb.exe : up.obj
   echo Building bounce.exe...
```

は次のように評価されます。

```makefile
leap.exe : jump.obj
# invokes an inference rule

bounce.exe : jump.obj up.obj
   echo Building bounce.exe...

climb.exe : up.obj
   echo Building bounce.exe...
```

### <a name="targets-in-multiple-description-blocks"></a><a name="targets-in-multiple-description-blocks"></a>複数の記述ブロック内のターゲット

異なるコマンドを使用して複数の記述ブロック内のターゲットを更新するには、2 つの連続したコロン (::)ターゲットと依存の間で。

```makefile
target.lib :: one.asm two.asm three.asm
    ml one.asm two.asm three.asm
    lib target one.obj two.obj three.obj
target.lib :: four.c five.c
    cl /c four.c five.c
    lib target four.obj five.obj
```

### <a name="dependency-side-effects"></a><a name="dependency-side-effects"></a>依存関係の副作用

コロン (:) でターゲットを指定できます。異なる場所にある 2 つの依存関係行で。 コマンドが 1 行の後にだけ出現する場合、NMAKE は、行が隣接または結合された場合と同様に依存関係を解釈します。 コマンドを持たない依存関係の推論規則は呼び出されません。 代わりに、NMAKE は、依存関係が 1 つの記述ブロックに属していると見なし、他の依存関係で指定されたコマンドを実行します。 次のルールのセットを考えてみます。

```makefile
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
```

は次のように評価されます。

```makefile
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

この効果は、二重コロン (`::`) を使用した場合には発生しません。 たとえば、次のルールのセットを次に示します。

```makefile
bounce.exe :: jump.obj
   echo Building bounce.exe...

bounce.exe :: up.obj
```

は次のように評価されます。

```makefile
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
# invokes an inference rule
```

### <a name="pseudotargets"></a><a name="pseudotargets"></a>擬似ターゲット

*擬似ターゲット*は、依存関係行のファイル名の代わりに使用されるラベルです。 これは存在しないファイルとして解釈され、最新ではなくなります。 NMAKE は、擬似ターゲットのタイムスタンプが、すべての依存の最新のタイムスタンプと同じであると仮定します。 従属が存在しない場合は、現在の時刻が想定されます。 擬似ターゲットがターゲットとして使用される場合、そのコマンドは常に実行されます。 依存として使用される疑似ターゲットは、別の依存関係のターゲットとしても表示される必要があります。 ただし、依存関係にはコマンド ブロックを用意する必要はありません。

擬似ターゲット名は、ターゲットのファイル名の構文規則に従います。 ただし、名前に拡張子がない場合は、ファイル名の 8 文字の制限を超えることができ、最大 256 文字の長さになります。

擬似ターゲットは、NMAKE で複数のターゲットを自動的に作成する場合に便利です。 NMAKE は、コマンド ラインで指定されたターゲットのみを作成します。 または、コマンドラインターゲットが指定されていない場合、makefile の最初の依存関係の最初のターゲットのみがビルドされます。 コマンド ラインに個別に一覧表示せずに、複数のターゲットを作成するように NMAKE に指示できます。 擬似ターゲットを含む依存関係を持つ記述ブロックを作成し、その依存としてビルドするターゲットを一覧表示します。 次に、この記述ブロックをメイクファイルに最初に配置するか、または NMAKE コマンド ラインで擬似ターゲットを指定します。

この例では、UPDATE は疑似ターゲットです。

```makefile
UPDATE : *.*
!COPY $** c:\product\release
```

UPDATE が評価されると、NMAKE は現在のディレクトリ内のすべてのファイルを指定されたドライブとディレクトリにコピーします。

次のメイクファイルでは、擬似ターゲット`all`は、`project1.exe`コマンドライン`project2.exe`でターゲット`all`が指定されているか、または指定されていない場合の両方を構築します。 疑似ターゲット`setenv`は、ファイルが更新される前`.exe`に LIB 環境変数を変更します。

```makefile
all : setenv project1.exe project2.exe

project1.exe : project1.obj
    LINK project1;

project2.exe : project2.obj
    LINK project2;

setenv :
    set LIB=\project\lib
```

## <a name="dependents"></a><a name="dependents"></a>扶養 家族

依存行で、有効なファイル名または[疑似対象](pseudotargets.md)を使用して`:`、コロン (`::`) または二重コロン ( ) の後に 0 個以上の従属を指定します。 1 つ以上のスペースまたはタブを使用して、複数の従属を分離します。 依存ファイルでは大文字と小文字は区別されません。 パスはファイル名で許可されています。

### <a name="inferred-dependents"></a><a name="inferred-dependents"></a>推定被扶養者

依存行に明示的にリストする依存と共に、NMAKE は*推論された従属*を想定できます。 推論される依存は推論規則から派生し、明示的な依存の前に評価されます。 推定される依存がターゲットと比較して最新の状態にならない場合、NMAKE は依存関係のコマンド ブロックを呼び出します。 推定される依存が存在しない場合、または自身の依存と比較して最新ではない場合、NMAKE は最初に推定される依存を更新します。 推論される従属の詳細については、[推論規則](inference-rules.md)を参照してください。

### <a name="search-paths-for-dependents"></a><a name="search-paths-for-dependents"></a>依存のパスを検索する

依存する各ファイルに対して、オプションの検索パスを指定できます。 検索するディレクトリのセットを指定する構文を次に示します。

> **{**_ディレクトリ_\[**;**_ディレクトリ_.)**}**_依存_

ディレクトリ名を中かっこ (`{ }`) で囲みます。 セミコロン ( )`;`で複数のディレクトリを区切ります。 スペースやタブは使用できません。 NMAKE は、現在のディレクトリで最初に依存を検索し、次に指定された順序でディレクトリの一覧を検索します。 マクロを使用して、検索パスの一部または全部を指定できます。 指定された依存ファイルだけがこの検索パスを使用します。

#### <a name="directory-search-path-example"></a>ディレクトリ検索パスの例

次の依存関係行は、検索用のディレクトリ仕様を作成する方法を示しています。

```makefile
reverse.exe : {\src\omega;e:\repo\backwards}retro.obj
```

ターゲット`reverse.exe`には、1 つの`retro.obj`依存する が含されます。 中かっこで囲まれたリストは、2 つのディレクトリを指定します。 NMAKE は`retro.obj`、最初にカレント ディレクトリ内を検索します。 ディレクトリが存在しない場合は、NMAKE は`\src\omega`ディレクトリを検索してから`e:\repo\backwards`、ディレクトリを検索します。

## <a name="see-also"></a>関連項目

[NMAKE リファレンス](nmake-reference.md)

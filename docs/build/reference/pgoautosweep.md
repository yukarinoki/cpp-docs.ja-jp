---
title: PgoAutoSweep |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- PgoAutoSweep
- PogoAutoSweepA
- PogoAutoSweepW
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 988a73dd8c4ad6929ef04691ad1959df7ea7bdd7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379498"
---
# <a name="pgoautosweep"></a>PgoAutoSweep

`PgoAutoSweep` ファイルに現在のプロファイル カウンター情報を保存し、カウンターをリセットします。 プロファイル ガイド付き最適化の実行中のプログラムからすべてのプロファイル データを最適化のビルドの後で使用するために .pgc ファイルに書き込むのトレーニング中に、関数を使用します。

## <a name="syntax"></a>構文

```cpp
void PgoAutoSweep(const char* name);    // ANSI/MBCS
void PgoAutoSweep(const wchar_t* name); // UNICODE
```

### <a name="parameters"></a>パラメーター

*name*<br/>
保存されている .pgc ファイルを識別する文字列。

## <a name="remarks"></a>コメント

呼び出すことができます`PgoAutoSweep`のアプリケーションから保存し、アプリケーションの実行中に任意の時点で、プロファイル データをリセットします。 インストルメントされたビルドで`PgoAutoSweep`現在のプロファイリング データをキャプチャ、ファイルを保存およびプロファイル カウンターをリセットします。 呼び出すことと同等である、 [pgosweep](pgosweep.md)実行可能ファイルで特定の時点でコマンド。 最適化されたビルド`PgoAutoSweep`は行いません。

カウンター データを保存するプロファイルがという名前のファイルに配置されます*base_name*-*名前*!*値*.pgc、場所*base_name* 、実行可能ファイルの基本名は、*名前*に渡されたパラメーター `PgoAutoSweep`、および*値*通常、単調に増加する数、ファイル名の競合を防ぐために、一意な値です。

によって作成された .pgc ファイル`PgoAutoSweep`最適化された実行可能ファイルを作成するための .pgd ファイルにマージする必要があります。 使用することができます、 [pgomgr](pgomgr.md)コマンドを実行して、マージします。

最適化のビルド中を使用して、リンカーにマージされた .pgd ファイルの名前を渡すことができます、 **PGD =**_filename_への引数、 [/USEPROFILE](useprofile.md)リンカー オプション、または使用して、非推奨 **/PGD**リンカー オプション。 という名前のファイルには、.pgc ファイルをマージするかどうかは*base_name*.pgd、する必要はありません、コマンドラインのファイル名を指定するため、リンカーが既定でこのファイル名を取得します。

`PgoAutoSweep`機能は、スレッドの安全性設定は、インストルメント化されたビルドを作成するときに指定します。 既定の設定を使用するかを指定する場合、 **noexact は、** への引数、 [/GENPROFILE または/FASTGENPROFILE]()呼び出しをリンカー オプション、`PgoAutoSweep`スレッド セーフではありません。 **EXACT**引数作成スレッド セーフであるより精度がより低速でインストルメント化された実行可能ファイルです。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|`PgoAutoSweep`|\<pgobootrun.h>|

実行可能ファイルは、リンクされたライブラリに pgobootrun.lib ファイルを含める必要があります。 このファイルは、VC のライブラリ ディレクトリをサポートするアーキテクチャごとに、Visual Studio のインストールに含まれます。

## <a name="example"></a>例

使用して次の例`PgoAutoSweep`に 2 つ作成します。実行中にさまざまなポイントで PGC ファイル。 最初にするまで実行時の動作を説明するデータが含まれています`count`3 に等しく、2 つ目には、アプリケーションの終了時の直前までこのポイント以降に収集されたデータが含まれています。

```cpp
// pgoautosweep.cpp
// Compile by using: cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp
// Link to instrument: link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj
// Run to generate data: pgoautosweep
// Merge data by using command line pgomgr tool:
// pgomgr /merge pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc pgoautosweep.pgd
// Link to optimize: link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj

#include <iostream>
#include <windows.h>
#include <pgobootrun.h>

void func2(int count)
{
    std::cout << "hello from func2 " << count << std::endl;
    Sleep(2000);
}

void func1(int count)
{
    std::cout << "hello from func1 " << count << std::endl;
    Sleep(2000);
}

int main()
{
    int count = 10;
    while (count--)
    {
        if (count < 3)
            func2(count);
        else
        {
            func1(count);
            if (count == 3)
            {
                PgoAutoSweep("func1");
            }
        }
    }
    PgoAutoSweep("func2");
}
```

開発者コマンド プロンプトで、このコマンドを使用してオブジェクト ファイルにコードをコンパイルします。

`cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp`

このコマンドを使用してトレーニング用にインストルメントされたビルドを生成します。

`link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj`

トレーニング データのキャプチャにインストルメント化された実行可能ファイルを実行します。 呼び出しによってデータ出力`PgoAutoSweep`pgoautosweep func1 をという名前のファイルに保存されます。 1.pgc と pgoautosweep func2! 1.pgc です。 これを実行すると、プログラムの出力は次のようになります。

```Output
hello from func1 9
hello from func1 8
hello from func1 7
hello from func1 6
hello from func1 5
hello from func1 4
hello from func1 3
hello from func2 2
hello from func2 1
hello from func2 0
```

実行して、プロファイルのトレーニング データベースに保存されたデータをマージ、 **pgomgr**コマンド。

`pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc`

このコマンドの出力では、次のようになります。

```Output
Microsoft (R) Profile Guided Optimization Manager 14.13.26128.0
Copyright (C) Microsoft Corporation. All rights reserved.

Merging pgoautosweep-func1!1.pgc
pgoautosweep-func1!1.pgc: Used  3.8% (22304 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
Merging pgoautosweep-func2!1.pgc
pgoautosweep-func2!1.pgc: Used  3.8% (22424 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
```

今すぐこのトレーニング データを使用して、最適化されたビルドを生成することができます。 最適化された実行可能ファイルをビルドするのにには、このコマンドを使用します。

`link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj`

```Output
Microsoft (R) Incremental Linker Version 14.13.26128.0
Copyright (C) Microsoft Corporation.  All rights reserved.

Merging pgoautosweep!1.pgc
pgoautosweep!1.pgc: Used  3.9% (22904 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
  Reading PGD file 1: pgoautosweep.pgd
Generating code

0 of 0 ( 0.0%) original invalid call sites were matched.
0 new call sites were added.
294 of 294 (100.00%) profiled functions will be compiled for speed
348 of 1239 inline instances were from dead/cold paths
294 of 294 functions (100.0%) were optimized using profile data
16870 of 16870 instructions (100.0%) were optimized using profile data
Finished generating code
```

## <a name="see-also"></a>関連項目

[ガイド付き最適化のプロファイル](profile-guided-optimizations.md)<br/>
[pgosweep](pgosweep.md)<br/>

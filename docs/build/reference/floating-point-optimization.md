---
title: Microsoft Visual C の浮動小数点の最適化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35c9263fa6252469124eefb0dfd575ef5bd2ac34
ms.sourcegitcommit: 5e932a0e110e80bc241e5f69e3a1a7504bfab1f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2018
---
# <a name="microsoft-visual-c-floating-point-optimization"></a>Microsoft Visual C 浮動小数点の最適化

浮動小数点のセマンティクスを管理するための Microsoft C コンパイラのメソッドを使用して浮動小数点コードを最適化するハンドルを取得します。 浮動小数点コードに対して唯一の安全な最適化を実行するようにしながら、高速なプログラムを作成します。

## <a name="optimization-of-floating-point-code-in-c"></a>C++ での浮動小数点コードの最適化

最適化の C++ コンパイラは、マシン語コードにソース コードを変換するだけでなく、効率の向上や、サイズを小さくように命令を整列します。 残念ながら、多くの一般的な最適化では、安全で浮動小数点演算を適用するときに必ずしもないです。 これの良い例は、David されるとおりに「新機能すべてコンピューター科学者必要があります知るは浮動小数点算術演算子」から次の合計アルゴリズムで確認できます*コンピューティング アンケート*、年 1991年 3 月年 pg です。 203:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0, C=0, Y, T;
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = T;
   }
   return sum;
}
```

この関数は追加 n **float**配列のベクトル内の値`A`です。 ループ本体内部では、アルゴリズムは、合計の次の手順に適用されます「補正」値を計算します。 このメソッドは、累積的なエラーの丸め時の複雑さが o (n) を維持したまま、単純な合計と比較して大幅に減ります。

Naïve C コンパイラは、浮動小数点演算の実数値演算と同じ代数的な規則に従っているように思われがちです。 このようなコンパイラ結論付けることもありますし、誤っています。

> C = T の合計 - Y = = > (合計 + Y) の合計 - Y = = > 0 になります。

つまり、C の見かけ上の値は定数ゼロでは常にします。 この定数値が後続の式に反映し、ループの本体は単純な合計に減少します。 正確である

> Y [i] - C の = = = > Y = [i]<br/>T = 合計 + Y = = > T = 合計 + [i]<br/>合計 = T = = > 合計 = 合計 + [i]

したがって、naïve コンパイラの論理変換に、`KahanSum`関数になります。

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0; // C, Y & T are now unused
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

変換アルゴリズムが高速で、*正確に表した、プログラマの意図がまったくない*です。 慎重に作成されたエラーの修正が完全に削除され、ダイレクト合計アルゴリズムでは、関連付けられているすべてのエラーで残っているはします。

当然のことながら高度な C++ コンパイラはその代数を認識はルール実際の算術演算一般的には適用されません浮動小数点算術演算子です。 ただし、高度な C++ コンパイラも可能性がありますも正しく解釈されないプログラマの意図します。

レジスタにできるだけ (と呼ばれる「のレジスタ格納」値) に多くの値を保持しようとする一般的な最適化を検討してください。 `KahanSum`例では、この最適化を試みるランタイム変数`C`、`Y`と`T`ループ本体でのみ使用されているためです。 登録の有効桁数が 23bits (単一) ではなく (double) 52bits の場合は、この最適化効果的に型を昇格させます`C`、`Y`と`T`入力**二重**です。 Sum 変数が同様にレジスタでない場合は、単精度にエンコードが残ります。 これは変換のセマンティクス`KahanSum`以下

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0;
   double C=0, Y, T; // now held in-register
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = (float) T;
   }
   return sum;
}
```

`Y`、`T`と`C`は今すぐ計算高い精度では、このエンコードが生じる内の値に応じて正確さに欠ける結果`A[]`です。 したがっても一見無害な最適化があります不適切な結果。

これらの最適化の問題は、「注意が必要」浮動小数点コードに制限はありません。 単純な浮動小数点のアルゴリズムは、適切に最適化されたときに失敗します。 ダイレクト合計の単純なアルゴリズムを検討してください。

```cpp
float Sum( const float A[], int n )
{
   float sum=0;
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

いくつかの浮動小数点ユニットが複数の操作を同時に実行できるため、コンパイラは、スカラー リダクション最適化が参加こともできます。 この最適化は、次のように、上記の単純な Sum 関数を効果的に変換します。

```cpp
float Sum( const float A[], int n )
{
   int n4 = n-n%4; // or n4=n4&(~3)
   int i;
   float sum=0, sum1=0, sum2=0, sum3=0;
   for (i=0; i<n4; i+=4)
   {
      sum = sum + A[i];
      sum1 = sum1 + A[i+1];
      sum2 = sum2 + A[i+2];
      sum3 = sum3 + A[i+3];
   }
   sum = sum + sum1 + sum2 + sum3;
   for (; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

関数には、各ステップで同時に処理できる 4 つの個別の総和ここでは保持します。 最適化された関数ははるかに高速ようになりましたが、最適な結果が最適化されていない結果とは大きく異なるできます。 この変更を行ったでは、コンパイラは、浮動小数点加算の連想; を前提としてください。つまり、これら 2 つの式が同等である:`(a + b) + c == a + (b + c)`です。 ただし、結合規則は常に持ちません浮動小数点数の場合は true。 代わりとしての合計を計算します。

```cpp
sum = A[0]+A[1]+A[2]+...+A[n-1];
```

変換後の関数は、結果としてようになりましたを計算します。

```cpp
sum = (A[0]+A[4]+A[8]+...)
    + (A[1]+A[5]+A[9]+...)
    + (A[2]+A[6]+A[10]+...)
    + (A[3]+A[7]+A[11]+...);
```

値によって`A[]`、この追加操作の順序を異なると、予期しない結果が生じる可能性があります。 さらに複雑なことをこのような最適化を予測して、それらを適切に補正するプログラマによってができます。 この場合、プログラムは、配列を構築できます`A`を異なる順序で最適化された合計が期待どおりの結果を生成するようにします。 さらに、多くの場合、最適化された結果の精度があります「近づいた」。 これは、最適化は、説得力のある速度の利点を提供する場合に特に当てはまります。 ビデオ ゲームには、できるだけはるかに高速化が、正確な浮動小数点演算を必要としない多くの場合、たとえば、必要があります。 コンパイラ者は、速度と精度の多くの場合、さまざまな目標を制御するプログラマのためのメカニズムを提供したがって必要があります。

一部のコンパイラでは、最適化の種類ごとに個別のスイッチを提供することによって、速度と精度のバランスを解決します。 これにより、開発者は、特定のアプリケーションの浮動小数点数の精度に変更を引き起こす最適化を無効にできます。 このソリューションは、高度なコンパイラに制御を提供して可能性があります、他の問題をいくつか導入されています。

- 明確ではない多くの場合、有効または無効にするスイッチです。
- 任意の 1 つの最適化を無効にすると、非浮動小数点コードのパフォーマンスが低下する可能性があります。
- その他のスイッチはそれぞれが多く新しいスイッチの組み合わせです。短時間の組み合わせの数は扱いにくくなります。

したがって最適化ごとの個別のスイッチを提供するように見えますが魅力的なこのようなコンパイラを使用できます厄介で面倒と信頼性の低い。

多くの C++ コンパイラを提供して、*整合性*浮動小数点モデルでは、(を通じて、 **/Op**または **/fltconsistency**切り替える) 準拠のプログラムを作成する開発者を有効にします。厳密な浮動小数点セマンティクスです。 、関与している場合このモデルにより、コンパイラ非浮動小数点コード用のこれらの最適化しながら浮動小数点演算でほとんどの最適化を使用できません。 整合性モデルでは、暗い側ただしはします。 異なる FPU アーキテクチャのほぼすべての実装で予測可能な結果を返すために **/Op**ラウンドの中間式をユーザーには指定された有効桁数です。 たとえば、次の式。

```cpp
float a, b, c, d, e;
// . . .
a = b * c + d * e;
```

繰り返し可能な一貫性のある結果を生成するために **/Op**、次のように実装された場合に、この式は評価を取得します。

```cpp
float x = b  *c;
float y = d * e;
a = x + y;
```

最終的な結果が丸め誤差の単精度から発生*式の評価の各ステップで*です。 この解釈 C++ セマンティクス規則に違反厳密には、浮動小数点式を評価する最良の方法ではほとんどありません。 通常、中間結果を得るには実用的では、有効桁数と高を計算するより望ましくです。 たとえば、はずの式を計算`a = b * c + d * e`ようより高い精度で

```cpp
double x = b * c;
double y = d * e;
double z = x + y;
a = (float)z;
```

さらに優れた手法または

```cpp
long double x = b * c;
long double y = d * e
long double z = x + y;
a = (float)z;
```

高い有効桁数で中間結果を計算するときに、最終的な結果が大幅に精度が上がります。 皮肉、整合性モデルを採用するには、エラー発生の可能性は増加を安全でない最適化を無効にしてエラーを減らすために、ユーザーがしようとしている場合に正確にします。 したがって整合性モデルが大幅に低下効率精度の向上の保証が同時に提供しないときにします。 重大な数値プログラマにこれは非常に良好トレードオフのようなよう、モデルは通常、受信していないこと、主な理由。

以降でバージョン 8.0 (C++® 2005)、Microsoft C コンパイラは、はるかに優れたアプローチを提供します。 これにより、プログラマは 3 つの一般的な浮動小数点モードのいずれかを選択: fp:/fp:fast 正確であり、fp: 厳密。

- Fp: 正確で、安全な最適化のみに浮動小数点コードは、実行とは異なり **/Op**、中級者向けの計算が最高の実践的な精度で実行され一貫しています。
- /fp:fast モードでは、精度を犠牲にして比較的余裕のない最適化を許可する浮動小数点の規則を緩和します。
- fp: 厳格モード fp の一般的な正確性をすべての提供: fp 例外のセマンティクスを有効にして、FPU 環境の変更 (丸めの方向など、登録の有効桁数の変更など) が存在する場合、無効な変換を回避しながら正確です。

浮動小数点例外のセマンティクスで制御できましていない個別にコマンド ライン スイッチまたはコンパイラ プラグマ; のいずれか既定では、浮動小数点例外のセマンティクスは fp で無効になっています: 正確かつ fp 下で有効になっている: 厳密なです。 コンパイラでは、FPU 環境と小文字の区別と短縮など特定浮動小数点特定の最適化を制御も提供します。 この単純なモデルでは、開発者が大幅に向上が多すぎますコンパイラ スイッチの負担や望ましくない副作用の取引関係なしの浮動小数点コードのコンパイルが細かく制御できます。

## <a name="the-fpprecise-mode-for-floating-point-semantics"></a>Fp: 浮動小数点のセマンティクスのための正確なモード

既定の浮動小数点セマンティクス モードは fp: 正確です。 このモードを選択すると、コンパイラに厳密に従った安全性規則のセットを浮動小数点演算を最適化するときにします。 これらの規則は、浮動小数点演算の精度を維持しながら、効率的なマシン語コードを生成するコンパイラを許可します。 高速の運用を容易にするプログラム、fp: (ただし、明示的に有効にできます)、正確なモデルが浮動小数点例外のセマンティクスを無効にします。 Microsoft に fp が選択されています: 高速で正確なの両方のプログラムを作成するため、既定の浮動小数点モードとして正確です。

Fp を明示的に要求する: precise モードを使用して、コマンド ライン コンパイラを使用して、 [/fp: 正確な](fp-specify-floating-point-behavior.md)スイッチします。

> cl/fp:strict: 正確な source.cpp

Fp を使用するようにコンパイラに指示この: 正確なセマンティクス source.cpp ファイルのコードを生成するときにします。 Fp: を使用して、関数によってごとに正確なモデルを呼び出すことも、 [float_control コンパイラ プラグマ](#the-float-control-pragma)です。

Fp: precise モードは、コンパイラはしない浮動小数点演算の精度を与えるすべての最適化を実行します。 コンパイラの割り当てで正しく丸め常に、丸めないおよび関数呼び出し、あり中間丸めは一貫してで実行すると同じ精度 FPU の登録とします。 既定では、し、短縮形などの安全な最適化が有効にします。 既定では、例外のセマンティクスと FPU 環境と小文字の区別が無効です。

|fp: 正確なセマンティクス|説明|
|-|-|
|セマンティクスの丸め処理を行う|丸めないに割り当て、明示的な丸めと関数を呼び出します。 登録の有効桁数で中間式が評価されます。|
|代数変換|非連想、非分配の浮動小数点演算に厳密な準拠している変換が常に保証する場合を除き、同じ結果を生成します。|
|短縮形|既定では許可されます。 詳細については、セクションを参照してください。 [fp_contract プラグマ](#the-fp-contract-pragma)です。|
|浮動小数点の評価の順序|コンパイラは、可能性がありますの順序を変更浮動小数点式の評価を最終結果は変更されません。|
|FPU 環境のアクセス|既定では無効です。 詳細については、セクションを参照してください。 [fenv_access プラグマ](#the-fenv-access-pragma)です。 既定の有効桁数と丸めモードが使用されます。|
|浮動小数点例外のセマンティクス|既定では無効です。 詳細については、次を参照してください。 [/fp: 除く](fp-specify-floating-point-behavior.md)です。|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpprecise"></a>Fp 浮動小数点式のセマンティクスの丸め処理を行う: 正確な

Fp: 正確なモデルが常に最上位の実用的な精度、式の評価で特定の時点でのみに明示的に丸め処理での中間の計算を実行します。 4 つの場所は、常にユーザーが指定した有効桁数に丸め処理を行う: (a)、割り当てが行われると、(b)、型が実行されると、(c) 浮動小数点値が渡されたときに、引数として、関数およびから浮動小数点値が返されます (d) ときに、関数。 中間結果の精度はプラットフォームによって異なります、中級者向けの計算は、登録の有効桁数で常に実行され、ので (が、有効桁数は常に指定したユーザーには、少なくとも正確な有効桁数)。

次のコードの代入式を検討してください。 代入演算子 '=' の右辺の式は登録の有効桁数に計算し、代入式の左辺の型に明示的に丸めします。

```cpp
float a, b, c, d;
double x;
...
x = a*b + c*d;
```

として計算されます。

```cpp
float a, b, c, d;
double x;
...
register tmp1 = a*b;
register tmp2 = c*d;
register tmp3 = tmp1+tmp2;
x = (double) tmp3;
```

中間結果を明示的に丸めるに、型が導入されました。 たとえば、前のコードを追加することで変更する場合、明示的な型キャスト、中間式 (c * d) は、型キャストの型に丸められます。

```cpp
float a, b, c, d;
double x;
// . . .
x = a*b + (float)(c*d);
```

として計算されます。

```cpp
float a, b, c, d;
double x;
// . . .
register tmp1 = a*b;
float tmp2 = c*d;
register tmp3 = tmp1+tmp2;
x = (double) tmp3;
```

1 つこの丸め方式は一部の見かけ上と同じ変換は同じ意味で実際にはありません。 たとえば、次の変換には、2 つの代入式に 1 つの代入式が分割されています。

```cpp
float a, b, c, d;
// . . .
a = b*(c+d);
```

相当

```cpp
float a, b, c, d;
// . . .
a = c+d;
a = b*a;
```

同様にします。

```cpp
a = b*(c+d);
```

相当

```cpp
a = b*(a=c+d);
```

これらのエンコーディングは、それぞれの 2 つ目のエンコーディングが、追加の代入演算を導入していますが、そのため、ポイント、丸め処理と同じセマンティクスがありません。

関数は、浮動小数点値を返すときに、値は、関数の型に丸められます。 関数に浮動小数点値がパラメーターとして渡されると、値は、パラメーターの型に丸められます。 例えば:

```cpp
float sumsqr(float a, float b)
{
   return a*a + b*b;
}
```

として計算されます。

```cpp
float sumsqr(float a, float b)
{
    register tmp3 = a*a;
    register tmp4 = b*b;
    register tmp5 = tmp3+tmp4;
    return (float) tmp5;
}
```

同様にします。

```cpp
float w, x, y, z;
double c;
...
c = symsqr(w*x+y, z);
```

として計算されます。

```cpp
float x, y, z;
double c;
...
register tmp1 = w*x;
register tmp2 = tmp1+y;
float tmp3 = tmp2;
c = symsqr( tmp3, z);
```

### <a name="architecture-specific-rounding-under-fpprecise"></a>アーキテクチャ固有の丸め fp: 正確な

|プロセッサ|中間式の有効桁数の丸め処理を行う|
|-|-|
|x86|中間式は、16 ビットの指数部によって提供される拡張の範囲と既定 53 ビット精度で計算されます。 これらの 53:16 値は、メモリ (関数の呼び出し中に発生することができます) にで「書き込まれた」は、ときに、11 ビットに拡張の指数部の範囲に絞り込まれます。 つまり、書き込まれた値は、11 ビット指数部のみ使用して、標準の倍精度形式にキャストされます。<br/>ユーザーが拡張の 64 ビット精度浮動小数点制御ワードを使用して、変更することにより中間丸めに切り替えることがあります`_controlfp`し FPU 環境のアクセスを有効にして (を参照してください[fenv_access プラグマ](#the-fenv-access-pragma))。 ただし、メモリには、拡張精度レジスタの値が書き込まれた、ときに、中間結果が倍精度にまだ丸められます。<br/>この特定のセマンティクスは変更されます。|
|amd64|Amd64 に対して FP セマンティクスは、他のプラットフォームからやや異なります。 パフォーマンス向上のための代わりに使用できる最も長い有効桁数でのいずれかのオペランドの最も有効桁数で中間操作が計算されます。  オペランドより広い有効桁数を使用して計算する計算を強制するには、ユーザーのサブ式内の少なくとも 1 つのオペランドでキャスト操作を導入する必要があります。<br/>この特定のセマンティクスは変更されます。|

### <a name="algebraic-transformations-under-fpprecise"></a>代数変換 fp: 正確な

ときに、fp: precise モードが有効になっている、コンパイラは代数変換を実行しない*最終的な結果がおそらくと同一でない限り*です。 多くの算術演算の実数の使い慣れた代数ルール常に保持しない浮動小数点演算です。 たとえば、次の式は等価レアル、に対しては必ずしも浮動小数点数。

|フォーム|説明|
|-|-|
|`(a+b)+c = a+(b+c)`|結合ルールの追加|
|`(a*b)*c = a*(b*c)`|乗算の結合規則|
|`a*(b+c) = a*b + b*c`|加算経由での乗算の配布|
|`(a+b)(a-b) = a*a-b*b`|代数ファクタリング|
|`a/b = a*(1/b)`|逆数による除算です。|
|`a*1.0 = a`|乗法|

関数の概要の例に示されている`KahanSum`、コンパイラたくなるかもしれません大幅に高速のプログラムを生成するためにさまざまな代数変換を実行します。 このような代数変換に依存する最適化がほぼ常に正しくないを完全に安全である場合があります。 インスタンスでの除算を置き換えることが望ましい場合があります、*定数*乗法の逆関数の値での乗算で定数の値。

```cpp
const double four = 4.0;
double a, b;
...

a = b/four;
```

変換することがあります。

```cpp
const double four = 4.0;
const double tmp0 = 1/4.0;
double a, b;
...
a = b*tmp0;
```

これは、オプティマイザーに判断できるのでコンパイル時にその x の安全な変換 4.0/すべての浮動小数点値の x、無限大および NaN を含む x*(1/4.0) を = = です。 に乗算と除算演算を置き換えることで、コンパイラがいくつかのサイクルを節約できます — FPUs 除算では、直接実装していないが、コンパイラに近似逆数の組み合わせを生成し、乗算の追加が必要では特に記載されています。 コンパイラは fp 下で、このような最適化を実行できます。 正確な置換乗算生成正確な場合にのみ同じ結果になります、除算として。 コンパイラ可能性があります fp 単純な変換を実行しても: 正確な結果が同じです。 次の設定があります。

|フォーム|説明
|-|-|
|`(a+b) == (b+a)`|可換性ルールの追加|
|`(a*b) == (b*a)`|乗算の可換性ルール|
|`1.0*x*y == x*1.0*y == x*y*1.0 == x*y`|1.0 での乗算|
|`x/1.0*y == x*y/1.0 == x*y`|1.0 での除算|
|`2.0*x == x+x`|2.0 での乗算|

### <a name="contractions-under-fpprecise"></a>短縮形 fp: 正確な

多くの最新の浮動小数点ユニットの重要なアーキテクチャ機能は、中間丸めエラーを伴う単独操作としての追加後に乗算を実行する機能です。 Intel の Itanium アーキテクチャがこれらの各三項操作、結合する手順を説明するなど、(、*b + c)、(、* b c) と (c、* b)、単一の浮動小数点命令 (fma、fms と fnma それぞれ)。 1 つの手順は乗算して、追加手順については、個別の実行よりも高速より正確な製品の中間の丸め処理がないためです。 この最適化は、乗算インターリーブされるいくつかを含む関数を高速化し、操作を追加することができますが大幅にします。 たとえば、2 つの n 次元ベクトルのドット積を計算する次のアルゴリズムを検討してください。

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

この計算を実行できる一連の乗算の命令を追加、フォーム p の = p + x [i] * y [i] です。

縮小最適化個別に制御できますを使用して、`fp_contract`コンパイラ プラグマ。 既定では、fp: ので、処理速度と精度が向上し、短縮形の正確なモデルを使用します。 Fp:/fp:precise、コンパイラは縮小しない明示的な丸めを適用した式です。
使用例

```cpp
float a, b, c, d, e, t;
...
d = a*b + c;         // may be contracted
d += a*b;            // may be contracted
d = a*b + e*d;       // may be contracted into a mult followed by a mult-add
etc...

d = (float)a*b + c;  // won't be contracted because of explicit rounding

t = a*b;             // (this assignment rounds a*b to float)
d = t + c;           // won't be contracted because of rounding of a*b
```

### <a name="order-of-floating-point-expression-evaluation-under-fpprecise"></a>Fp 浮動小数点式の評価の順序: 正確な

浮動小数点式の評価の順序を保持している最適化は常に安全と fp 下にあるため許可されます。 正確なモードです。 単精度の 2 つの n 次元ベクトルのドット積を計算する次の関数を検討してください。 最初のコード ブロックは、元の関数ように、プログラマがエンコードする必要がありますの後に同じ関数で部分的なループ アンローリング最適化後にします。

```cpp
//original function
float dotProduct( float x[], float y[], int n )
{
   float p=0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}

//after a partial loop-unrolling
float dotProduct( float x[], float y[], int n )
{
   int n4= n/4*4; // or n4=n&(~3);
   float p=0;
   int i;

   for (i=0; i<n4; i+=4)
   {
      p+=x[i]*y[i];
      p+=x[i+1]*y[i+1];
      p+=x[i+2]*y[i+2];
      p+=x[i+3]*y[i+3];
   }

   // last n%4 elements
   for (; i<n; i++)
      p+=x[i]*y[i];

   return p;
}
```

この最適化の主な利点は、75% ループ条件分岐の数が減ることことです。 また、ループの本体の内部での操作の数を増やすことでコンパイラようになりましたがありますをさらに最適化する機会です。 たとえば、いくつか FPUs できる場合がありますを実行する、p = で乗算追加 x [i] * [i] x [i+1] の値を同時にフェッチ中におよび y [i+1]、次の手順で使用するためです。 この最適化の種類は、演算の順序を保持するのでの浮動小数点計算に完全にも安全です。

コンパイラが高速のコードを生成するために全体の操作の順序を変更すると便利なことがあります。 次のコードがあるとします。

```cpp
double a, b, c, d;
double x, y, z;
...
x = a*a*a + b*b*b + c*c*c;
...
y = a*a + b*b + c*c;
...
z = a + b + c;
```

最初に計算されている場合と同様に、プログラムがの結果を作成する C++ の意味ルールを示す x、y し、最後に z。 コンパイラは 4 つだけ使用可能な浮動小数点レジスタとします。 計算する、コンパイラが強制された場合 x、y、z の順序では次のセマンティクスでコードを生成することを選択して可能性があります。

```cpp
double a, b, c, d;
double x, y, z;
register r0, r1, r2, r3;
...
// Compute x
r0 = a;         // r1 = a*a*a
r1 = r0*r0;
r1 = r1*r0;
r0 = b;         // r2 = b*b*b
r2 = r0*r0;
r2 = r2*r0;
r0 = c;         // r3 = c*c*c
r3 = r0*r0;
r3 = r3*r0;
r0 = r1 + r2;
r0 = r0 + r3;
x = r0;         // x = r1+r2+r3
// . . .
// Compute y
r0 = a;         // r1 = a*a
r1 = r0*r0;
r0 = b;         // r2 = b*b
r2 = r0*r0;
r0 = c;         // r3 = c*c
r3 = r0*r0;
r0 = r1 + r2;
r0 = r0 + r3;
y = r0;         // y = r1+r2+r3
// . . .
// Compute z
r1 = a;
r2 = b;
r3 = c;
r0 = r1 + r2;
r0 = r0 + r3;
z = r0;         // z = r1+r2+r3
```

いくつか明確に重複した操作は、このエンコードがあります。 場合は、コンパイラは、C++ の意味ルールを厳密に従う、この順序では必要なプログラムが、各割り当てには、FPU 環境間のアクセス可能性があります。 ただし、fp の既定の設定: 正確なこれらの式の順序を変更することを許可するプログラムは、環境にアクセスしないかのように最適化するためにコンパイラを許可します。 逆の順序で、次のように、3 つの値を計算することによって、重複を削除するために解放されます。

```cpp
double a, b, c, d;
double x, y, z;
register r0, r1, r2, r3;
...
// Compute z
r1 = a;
r2 = b;
r3 = c;
r0 = r1+r2;
r0 = r0+r3;
z = r0;
...
// Compute y
r1 = r1*r1;
r2 = r2*r2;
r3 = r3*r3;
r0 = r1+r2;
r0 = r0+r3;
y = r0;
...
// Compute x
r0 = a;
r1 = r1*r0;
r0 = b;
r2 = r2*r0;
r0 = c;
r3 = r3*r0;
r0 = r1+r2;
r0 = r0+r3;
x = r0;
```

このエンコーディングは明確に非常に優れた約 40% で fp 命令の数を削減することです。 X の結果を y、z が、以前と同じが少ないオーバーヘッドで計算します。

Fp: 正確で、コンパイラも*インター レース*高速のコードを生成するために共通のサブ式です。 たとえば、とおり、二次方程式式のルートを計算するコードを記述する可能性があります。

```cpp
double a, b, c, root0, root1;
...
root0 = (-b + sqrt(b*b-4*a*c))/(2*a);
root1 = (-b - sqrt(b*b-4*a*c))/(2*a);
```

これらの式は、1 つの操作によってのみが異なる、プログラマが記述した各ルートの値が最も高い実際的な精度計算されるを保証するには、この方法です。 Fp: コンパイラは自由インター レースを root0 と有効桁数を失うことがなく、共通のサブ式を削除する root1 の計算に正確でします。 たとえば、次が削除余分な手順がいくつか正確な同じ回答を生成している間です。

```cpp
double a, b, c, root0, root1;
...
register tmp0 = -b;
register tmp1 = sqrt(b*b-4*a*c);
register tmp2 = 2*a;
root0 = (tmp0+tmp1)/tmp2;
root1 = (tmp0-tmp1)/tmp2;
```

その他の最適化は、特定の独立した式の評価を移動しようとします。 ループ本体内部で条件付き分岐が含まれますが、次のアルゴリズムを検討してください。

```cpp
vector<double> a(n);
double d, s;
// . . .
for (int i=0; i<n; i++)
{
   if (abs(d)>1.0)
      s = s+a[i]/d;
   else
      s = s+a[i]*d;
}
```

コンパイラは、ことを検出可能性があります、式の値 (abs(d) > 1) ループ本体にあるバリアント型ではありません。 これにより、コンパイラ「行う」場合は、次のように、上記のコードを変換する、ループの本体の外側のステートメント。

```cpp
vector<double> a(n);
double d, s;
// . . .
if (abs(d)>1.0)
   for (int i=0; i<n; i++)
      s = s+a[i]/d;
else
   for (int i=0; i<n; i++)
      s = s+a[i]*d;
```

変換後が不要になった条件付き分岐、ループの全体的なパフォーマンスが大幅に向上、ループ本体のいずれかでします。 この種類の最適化が完全に安全なので、式の評価 (abs(d) > 1.0) は他の式に依存しません。

FPU 環境アクセスまたは浮動小数点例外の場合が存在する場合は、セマンティックのフローを変更するための最適化のこれらの型は contraindicated します。 このような最適化は fp で使用可能なのみ: precise モード FPU 環境のアクセスと浮動小数点例外のセマンティクスは既定で無効になっています。 FPU 環境にアクセスする関数を使ってこのような最適化を無効に明示的に、`fenv_access`コンパイラ プラグマ。 同様に、浮動小数点例外を使用して関数を使用する必要があります、`float_control(except ... )`コンパイラ プラグマ (またはを使用して、 **/fp: を除く**コマンド ライン スイッチ)。

要約すると、fp: 正確なモードでは、コンパイラ、最終的な結果が改ざんされていないである条件で浮動小数点式の評価の順序を変更することと結果がなく依存 FPU 環境または浮動小数点例外。

### <a name="fpu-environment-access-under-fpprecise"></a>FPU 環境のアクセス fp: 正確な

ときに、fp: precise モードが有効な場合、コンパイラは、プログラムのアクセスまたは FPU 環境が変更はありません。 前述のように、この前提により、コンパイラの順序を変更または移動 fp の下の効率を向上させるために浮動小数点演算に: 正確です。

一部のプログラムを使用して浮動小数点丸め処理を行う方向を変更することがあります、`_controlfp`関数。 たとえば、一部のプログラムを上限計算し、エラー下限の算術演算で 2 回、同じ計算を実行することによって最初に負の無限大方向に丸め処理を行う、中に、中に正の無限大方向に丸め処理を行います。 FPU は、丸め処理を制御する便利な手段を提供するため、プログラマの FPU 環境を変更することにより、丸めモードを変更ことができます。 次のコードでは、FPU 環境を変更することにより、正確なエラーが浮動小数点の乗算のバインドを計算します。

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -&infin;
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );    // round to +&infin;
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

Fp: 正確で、常と見なされます既定 FPU 環境、オプティマイザーは無料でへの呼び出しを無視するように`_controlfp`cUpper に上記の割り当てを減らすと cLower を = =、* b; が正しくない結果を得られます明確にこのです。 このような最適化を防ぐためには、有効にする FPU 環境のアクセスを使用して、`fenv_access`コンパイラ プラグマ。

その他のプログラムは、FPU のステータス ワードを確認する浮動小数点の特定のエラーを検出しようとします。 たとえば、次のコードは、条件については、0 除算と不正確なを確認します。

```cpp
double a, b, c, r;
float x;
// . . .
_clearfp();
r = (a*b + sqrt(b*b-4*a*c))/(2*a);
if (_statusfp() & _SW_ZERODIVIDE)
   handle divide by zero as a special case
_clearfp();
x = r;
if (_statusfp() & _SW_INEXACT)
   handle inexact error as a special case
etc...
```

Fp: 正確で、最適化の式の評価の順序を変更する可能性がありますを変更する特定のエラーが発生するポイント。 プログラムのステータス ワードにアクセスする必要がありますを使用して FPU 環境のアクセスを有効にする、`fenv_access`コンパイラ プラグマ。

詳細については、セクションを参照してください。 [fenv_access プラグマ](#the-fenv-access-pragma)です。

### <a name="floating-point-exception-semantics-under-fpprecise"></a>Fp 浮動小数点例外のセマンティクス: 正確な

既定では、浮動小数点例外のセマンティクスは fp で無効になっています: 正確です。 ほとんどの C++ プログラマは、システムまたは C++ の例外を使用することがなく浮動小数点の例外条件を処理する優先します。 さらに、前述のように、浮動小数点例外のセマンティクスの無効化により、コンパイラのより柔軟な浮動小数点演算を最適化するときにします。 いずれかを使用して、 **/fp: を除く**スイッチまたは`float_control`fp を使用する場合は、浮動小数点例外のセマンティクスを有効にするプラグマ: 正確なモデルです。

詳細については、セクションを参照してください。[浮動小数点例外のセマンティクスを有効にする](#enabling-floating-point-exception-semantics)です。

## <a name="the-fpfast-mode-for-floating-point-semantics"></a>浮動小数点のセマンティクスのため、/fp:fast モード

/Fp:fast モードが有効にすると、コンパイラの制限を緩和規則その fp: 浮動小数点演算を最適化するときに、正確な使用します。 このモードは、浮動小数点の精度と正確性を犠牲にして速度の浮動小数点コードをさらに最適化するためにコンパイラを使用します。 正確な浮動小数点演算に依存しないプログラム/fp:fast モードを有効にすると、速度が大幅に向上があります。

/Fp:fast 浮動小数点モードが有効な場合を使用して、 [/fp:fast](fp-specify-floating-point-behavior.md)次のようにコマンド ライン コンパイラ スイッチ。

> cl/fp:fast source.cpp

この例では、コンパイラ source.cpp ファイルのコードを生成するときに、/fp:fast セマンティクスを使用するように指示します。 使用して、関数によってごとに、/fp:fast モデルを呼び出すことも、`float_control`コンパイラ プラグマ。

詳細については、セクションを参照してください。 [float_control プラグマ](#the-float-control-pragma)です。

/Fp:fast モードの場合、コンパイラは浮動小数点演算の精度の変更の最適化を実行可能性があります。 割り当てで正しく丸められない可能性があります、丸めないまたは関数呼び出し、コンパイラと中間丸め処理は常に実行されません。 浮動小数点の特定最適化、し、短縮形は常に有効にします。 浮動小数点例外のセマンティクスと FPU 環境と小文字の区別は、無効になっており、使用できなくなったがします。

|/fp:fast セマンティクス|説明
|-|-|
|セマンティクスの丸め処理を行う|丸めないに割り当て、明示的な丸めと関数の呼び出しを無視してかまいません。<br/>中間式は、登録のパフォーマンス要件に従った有効桁数未満に丸められます可能性があります。|
|代数変換|コンパイラは、式をに従って実数値連想、分配代数; を変換可能性があります。これらの変換は、正確なまたは適切である保証はありません。|
|短縮形|常に有効にします。プラグマを無効にすることはできません。 `fp_contract`|
|浮動小数点の評価の順序|コンパイラは、可能性がありますの順序を変更、浮動小数点式の評価などの変更が最終的な結果を変更する場合でもです。|
|FPU 環境のアクセス|無効になります。 使用できません|
|浮動小数点例外のセマンティクス|無効になります。 使用できません|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpfast"></a>/Fp:fast 浮動小数点式のセマンティクスの丸め処理を行う

Fp とは異なり: 正確なモデル、/fp:fast モデルは、最も便利な精度中級者向けの計算を実行します。 丸めないに割り当て、丸め処理を行うと、関数呼び出しには常には発生しません。 以下の最初の関数が 3 つの単精度の変数を導入するのインスタンス (`C`、`Y`と`T`)。 コンパイラは可能性がありますランタイム型の昇格の有効で、これらの変数に選択`C`、`Y`と`T`倍精度にします。

元の関数。

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0, C=0, Y, T;
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = T;
   }
   return sum;
}
```

変数のレジスタ格納します。

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0;
   double C=0, Y, T; // now held in-register
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = (float) T;
   }
   return sum;
}
```

この例では/fp:fast は元の関数の目的をならない点です。 最終的な結果を変数では、保持の最適化`sum`、正しい結果から非常に不安になる場合があります。

/Fp:fast、下、コンパイラは通常しようには、少なくとも、ソース コードで指定された精度を維持します。 ただし、一部のインスタンスで、コンパイラもかまいません中級者向けの式を実行する、*精度を下げる*ソース コードで指定します。 たとえば、最初のコード ブロックは、平方根算出関数のバージョンが倍精度を呼び出します。 コンパイラを倍精度への呼び出しを置換することができます/fp:fast の結果と関数のオペランドは明示的にキャストするとき、単精度などの特定の状況で、`sqrt`単精度への呼び出しに`sqrtf`関数。 キャストいることを確認してへ値ため`sqrt`登場値は 1 つの有効桁数に丸められます、丸め処理の代わりにこのだけが変更されます。 Sqrt に入ってくる値が倍精度値と、コンパイラは、この変換を実行、精度ビットの半分ほどが正しくない可能性があります。

元の関数

```cpp
double sqrt(double);
// . . .
double a, b, c;
float f1, f2;
// . . .
float length = (float)sqrt((float)(a*a + b*b + c*c));
float sum = (float) ((double)f1 + (double)f2);
```

最適化された関数

```cpp
float sqrtf(float)...
// . . .
double a, b, c;
float f1, f2;
// . . .
double tmp0 = a*a + b*b + c*c;
float tmp1 = tmp0;    // round of parameter value
float length = sqrtf(tmp1); // rounded sqrt result
float sum = f1 + f2;
```

ただし、正確さに欠けますこの最適化は、特に有益など、1 つの有効桁数、組み込みのバージョンの関数を提供するプロセッサを対象とするときに`sqrt`です。 依存関係にあるプラットフォームとコンテキストの両方は正確に同じとき、コンパイラが使用するこのような最適化です。

さらに、コンパイラに利用可能な有効桁数のレベルで実行が許可される中級者向けの計算の有効桁数の整合性を確保することはありません。 コンパイラは、コードで指定された有効桁数のレベルの管理には、少なくともしようとするは、ですが、/fp:fast、高速な以下のマシン語コードを生成するためにダウン キャスト中級者向けの計算をオプティマイザーを使用できます。 たとえば、コンパイラをいくつかの単精度に中間の乗算を丸めるに上記のコードをさらに最適化することがあります。

```cpp
float sqrtf(float)...
// . . .
double a, b, c;
float f1, f2;
// . . .
float tmp0 = a*a;     // round intermediate a*a to single-precision
float tmp1 = b*b;     // round intermediate b*b to single-precision
double tmp2 = c*c;    // do NOT round intermediate c*c to single-precision
float tmp3 = tmp0 + tmp1 + tmp2;
float length = sqrtf(tmp3);
float sum = f1 + f2;
```

このような追加丸め、低い精度浮動小数点ユニット、SSE2 などを使用して、中間の計算の一部を実行する可能性があります。 /Fp:fast 丸め処理の精度はあるため、プラットフォームによって異なります。1 つのプロセッサに対して適切にコンパイルされるコードは、別のプロセッサに適して必ずしも動作可能性があります。 速度の利点がありますが、精度の問題を上回るかどうかを決定するユーザーに任されています。

/Fp:fast 最適化は、特定の機能にとって特に問題である場合、浮動小数点モード切り替えることができるローカル fp: 正確なを使用して、`float_control`コンパイラ プラグマ。


### <a name="algebraic-transformations-under-fpfast"></a>/Fp:fast 代数変換

/Fp:fast モードでは、コンパイラを実行、一部の浮動小数点への安全でない代数変換は、式をポイントします。 たとえば、以下の安全でない最適化の場合は、/fp:fast 採用されている可能性があります。

||||
|-|-|-|
|元のコード|手順 1.|手順 2
|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = y – a – b;`<br/><br/>`c = x – z;`<br/><br/>`c = x * z;`<br/><br/>`c = x - z;`<br/><br/>`c = x + z;`<br/><br/>`c = z-x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x – 0;`<br/><br/>`c = x * 0;`<br/><br/>`c = x - 0;`<br/><br/>`c = x + 0;`<br/><br/>`c = 0 - x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x;`<br/><br/>`c = 0;`<br/><br/>`c = x;`<br/><br/>`c = x;`<br/><br/>`c = -x;`|

コンパイラでは手順 1. で監視される`z = y – a – b`は常に 0 に等しい。 これは、無効な監視では技術的には、/fp:fast 下にあることは許可します。 コンパイラは、すべて z 変数の後で使用する定数値 0 を反映します。 ステップ 2 で、さらに、コンパイラの最適化を観察することによって`x - 0 == x`、 `x * 0 == 0`, などです。ここでも、これらの観測値が厳密に有効でない場合でもは/fp:fast 下で許可されます。 最適化されたコードでは、はるかに高速になりますが、かなり低い精度またはでも正しくない場合もあります。

次 (安全でない) 代数的なルールのいずれかを利用すること、オプティマイザーによって/fp:fast モードが有効になっている場合。

|||
|-|-|
|フォーム|説明|
|`(a + b) + c = a + (b + c)`|結合ルールの追加|
|`(a * b) * c = a * (b * c)`|乗算の結合規則|
|`a * (b + c) = a * b + b * c`|加算経由での乗算の配布|
|`(a + b)(a - b) = a * a - b * b`|代数ファクタリング|
|`a / b = a * (1 / b)`|逆数による除算です。|
|`a * 1.0 = a, a / 1.0 = a`|乗法|
|`a ± 0.0 = a, 0.0 - a = -a`|加法|
|`a / a = 1.0, a - a = 0.0`|キャンセル|

/Fp:fast 最適化は、特定の機能にとって特に問題である場合、浮動小数点モード切り替えることができるローカル fp: 正確なを使用して、`float_control`コンパイラ プラグマ。

### <a name="order-of-floating-point-expression-evaluation-under-fpfast"></a>/Fp:fast 浮動小数点式の評価の順序

Fp とは異なり:/fp:precise、/fp:fast により、コンパイラに高速のコードを生成するために浮動小数点演算の順序を変更します。 したがって、/fp:fast 下にある一部の最適化では、式の目的の順序が保持されません可能性があります。 たとえば、次の 2 つの n 次元ベクトルのドット積を計算する関数を検討してください。

```cpp
float dotProduct( float x[], float y[],
                  int n )
{
   float p=0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

/Fp:fast、オプティマイザーが実行するのスカラー リダクション、`dotProduct`効果的に変換する関数を次のように機能します。

```cpp
float dotProduct( float x[], float y[],int n )
{
    int n4= n/4*4; // or n4=n&(~3);
    float p=0, p2=0, p3=0, p4=0;
    int i;

    for (i=0; i<n4; i+=4)
    {
        p+=x[i]*y[i];
        p2+=x[i+1]*y[i+1];
        p3+=x[i+2]*y[i+2];
        p4+=x[i+3]*y[i+3];
    }
    p+=p2+p3+p4;

    // last n%4 elements
    for (; i<n; i++)
    p+=x[i]*y[i];

    return p;
}
```

最適化されたバージョンの関数で 4 つの個別製品総和に同時に実行し、一緒に追加し、します。 この最適化の計算を高速化することができます、`dotProduct`ほどとしてによってターゲットではなく、最終的な結果によって 4 つの要素ので不正確である役に立たないをレンダリングしたりします。 このような最適化が 1 つの関数または翻訳単位にとって特に問題である場合は、浮動小数点モード切り替えることができるローカル fp: 正確なを使用して、`float_control`コンパイラ プラグマ。

## <a name="the-fpstrict-mode-for-floating-point-semantics"></a>Fp: 浮動小数点のセマンティクスのための厳格モード

ときに、fp: 厳格モードが有効にした場合、コンパイラはその fp をすべて同じ規則に従います: 浮動小数点演算を最適化するときに、正確な使用します。 このモードも浮動小数点例外のセマンティクスと、FPU 環境に小文字の区別を有効にし、短縮形などの特定の最適化を無効になります。 最も厳格モードの動作することをお勧めします。

Fp: 厳密な浮動小数点のモードが有効な場合を使用して、 [/fp: 厳密な](fp-specify-floating-point-behavior.md)次のようにコマンド ライン コンパイラ スイッチ。

> cl/fp: 厳密な source.cpp

この例 fp を使用するようにコンパイラに指示します。 source.cpp ファイルのコードを生成するときに、厳密な型指定します。 Fp: を使用して、関数によってごとに厳格なモデルを呼び出すことも、`float_control`コンパイラ プラグマ。

詳細については、セクションを参照してください。 [float_control プラグマ](#the-float-control-pragma)です。

Fp: 厳格モードは、コンパイラはことはありません浮動小数点演算の精度を与えるすべての最適化を実行します。 コンパイラの割り当てで正しく丸め常に、丸めないおよび関数呼び出し、あり中間丸めは一貫してで実行すると同じ精度 FPU の登録とします。 既定では、浮動小数点例外のセマンティクスと FPU 環境と小文字の区別が有効にします。 コンパイラは、すべてのケースの正確性を保証できないために、し、短縮形などの特定の最適化が無効です。

|fp: 厳密な型指定|説明|
|-|-|
|セマンティクスの丸め処理を行う|丸めないに割り当て、明示的な丸め、および関数呼び出し<br/>登録の有効桁数で中間式が評価されます。<br/>Fp と同じ: 正確な|
|代数変換|非連想、非分配の浮動小数点演算に厳密な準拠している変換が常に保証する場合を除き、同じ結果を生成します。<br/>Fp と同じ: 正確な|
|短縮形|常に無効になっています|
|浮動小数点の評価の順序|コンパイラは浮動小数点式の評価の順序を変更できません。|
|FPU 環境のアクセス|常に有効にします。|
|浮動小数点例外のセマンティクス|既定で有効になります。|

### <a name="floating-point-exception-semantics-under-fpstrict"></a>Fp 浮動小数点例外のセマンティクス: strict

Fp で既定では、浮動小数点例外のセマンティクスが有効になる: 厳格なモデルです。 これらのセマンティクスを無効にするには、いずれかを使用、 **/fp: を除く-** 切り替えるか、導入、`float_control(except, off)`プラグマ。

詳細については、セクションを参照して[浮動小数点例外のセマンティクスを有効にする](#enabling-floating-point-exception-semantics)と[float_control プラグマ](#the-float-control-pragma)です。

## <a name="the-fenvaccess-pragma"></a>Fenv_access プラグマ

使用法:

```cpp
#pragma fenv_access( [ on  | off ] )
```

[Fenv_access](../../preprocessor/fenv-access.md)プラグマは、FPU フラグ テストと FPU モードの変更が無効になる特定の最適化のためにコンパイラを使用します。 ときの状態`fenv_access`を無効にしたと見なすことがコンパイラ既定 FPU モードが有効では、FPU フラグにテストされていません。 Fp の既定では、環境のアクセスが無効になります: 正確なモードでは、これを明示的に有効にするこのプラグマを使用してもします。 Fp: 厳密な`fenv_access`は常に有効し、無効にすることはできません。 /Fp:fast、下にある`fenv_access`は常に無効になり、有効にすることはできません。

Fp」の説明に従って: 正確なセクションは、浮動小数点丸め処理を行う方向を使用して、いくつかのプログラマが変わることがあります、`_controlfp`関数。 たとえば、算術演算に上限と下限のエラーの境界を計算するため一部のプログラム計算を実行同じ 2 回、負の無限大方向に丸め処理中に最初に、正の無限大方向に丸め処理中にします。 FPU は、丸め処理を制御する便利な手段を提供するため、プログラマの FPU 環境を変更することにより、丸めモードを変更ことができます。 次のコードでは、FPU 環境を変更することにより、正確なエラーが浮動小数点の乗算のバインドを計算します。

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -infinity
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );       // round to +infinity
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

無効にすると、`fenv_access`プラグマは、FPU の既定の環境を想定するコンパイラは、ので、オプティマイザーはへの呼び出しを無視するために解放`_controlfp`に上記の割り当てを減らすと`cUpper = cLower = a*b`です。 有効な場合、ただし、`fenv_access`このような最適化を防止します。

プログラムでは、浮動小数点の特定のエラーを検出するために、FPU ステータス ワードを調べることもできます。 たとえば、次のコードは、条件については、0 除算と不正確なを確認します。

```cpp
double a, b, c, r;
float x;
// . . .
_clearfp();
r = (a*b + sqrt(b*b-4*a*c))/(2*a);
if (_statusfp() & _SW_ZERODIVIDE)
   handle divide by zero as a special case
_clearfp();
x = (a*b + sqrt(b*b-4*a*c))/(2*a);
if (_statusfp() & _SW_INEXACT)
   handle inexact error as a special case
etc...
```

ときに`fenv_access`は無効にすると、コンパイラしたがって FPU 状態チェックを可能性のある subverting、浮動小数点式の実行順序を並べ替える可能性があります。 有効にする`fenv_access`このような最適化を防止します。

## <a name="the-fpcontract-pragma"></a>Fp_contract プラグマ

使用法:

```cpp
#pragma fp_contract( [ on | off ] )
```

Fp」の説明に従って: 正確なセクションを省略形は、多くの最新の浮動小数点ユニットの基本的なアーキテクチャの機能です。 短縮形は、中間丸めエラーを伴う単独操作としての追加後に乗算を実行する機能を提供します。 1 つの手順は乗算して、追加手順については、個別の実行よりも高速より正確な製品の中間の丸め処理がないためです。 契約の操作の値を計算できます`(a*b+c)`両方の操作は、無限の精度を計算し、に切り上げられますか、浮動小数点数に最も近いです。 この最適化は、乗算インターリーブされるいくつかを含む関数を高速化し、操作を追加することができますが大幅にします。 たとえば、2 つの n 次元ベクトルのドット積を計算する次のアルゴリズムを検討してください。

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

この計算を実行できる一連の乗算に命令を追加、フォームの`p = p + x[i]*y[i]`します。

[Fp_contract](../../preprocessor/fp-contract.md)プラグマは、浮動小数点式を縮小できるかどうかを指定します。 既定では、fp: 正確なモードを使用し、短縮形ので、処理速度と精度が向上します。 短縮形は常に、/fp:fast モードを有効にします。 ただし、短縮形は、エラー状態の明示的な検出を覆すことができます、 `fp_contract` fp プラグマが常に無効になっています: 厳格モードです。 可能性のある式の例を縮小するときに、`fp_contract`プラグマが有効になっています。

```cpp
float a, b, c, d, e, t;
...
d = a*b + c;         // may be contracted
d += a*b;            // may be contracted
d = a*b + e*d;       // may be contracted into a mult followed by a mult-add etc...

d = (float)a*b + c;  // won't be contracted because of explicit rounding

t = a*b;             // (this assignment rounds a*b to float)
d = t + c;           // won't be contracted because of rounding of a*b
```

## <a name="the-floatcontrol-pragma"></a>Float_control プラグマ

**/Fp: 正確な**、 **/fp:fast**、 **/fp: 厳密な**と **/fp: を除く**スイッチ ファイルでのファイルのセマンティクスは浮動小数点の制御ベース。 [Float_control](../../preprocessor/float-control.md)プラグマは関数によってごとにこのようなコントロールを提供します。

使用法:

```cpp
#pragma float_control(push)
#pragma float_control(pop)
#pragma float_control( precise, on | off [, push] )
#pragma float_control( except, on | off [, push] )
```

プラグマ`float_control(push)`と`float_control(pop)`それぞれをプッシュして、浮動小数点モードと、スタックに [例外] オプションの現在の状態をポップします。 なおの状態、`fenv_access`と`fp_contract`プラグマには影響ありません`pragma float_control(push/pop)`です。

プラグマを呼び出して`float_control(precise, on)`が有効になり、 `float_control(precise, off)` precise モードのセマンティクスが無効になります。 同様に、このプラグマ`float_control(except, on)`が有効になり、`float_control(except, off)`例外のセマンティクスが無効になります。 正確なセマンティクスも有効になっているときの例外のセマンティクスのみ有効にすることができます。 ときに、省略可能な`push`が存在する場合の状態、`float_control`セマンティクスを変更する前にオプションがプッシュされます。

### <a name="setting-the-floating-point-semantic-mode-on-a-function-by-function-basis"></a>関数によってごとに浮動小数点のセマンティック モードの設定

コマンド ライン スイッチは、実際には、次の 4 つの異なる浮動小数点プラグマの設定の短縮形です。 関数によってごとに特定の浮動小数点セマンティクス モードを明示的に選択するには、次の表に示すように 4 つ浮動小数点オプション プラグマのそれぞれを選択します。

||||||
|-|-|-|-|-|
||float_control(precise)|float_control(except)|fp_contract|fenv_access|
|/fp: strict|日付|日付|オフ|日付|
|/fp: 厳密な/fp:strict: 以外の|日付|オフ|オフ|日付|
|/fp: 正確な|日付|オフ|日付|オフ|
|/fp:/fp:precise/fp:strict: 以外|日付|日付|日付|オフ|
|/fp:fast|オフ|オフ|日付|オフ|

たとえば、次明示的に有効/fp:fast セマンティクスです。

```cpp
#pragma float_control( except, off )   // disable exception semantics
#pragma float_control( precise, off )  // disable precise semantics
#pragma fp_contract(on)                // enable contractions
#pragma fenv_access(off)               // disable fpu environment sensitivity
```

> [!Note]
> 例外のセマンティクスは、"precise"のセマンティクスを切る前に、オフにする必要があります。

## <a name="enabling-floating-point-exception-semantics"></a>浮動小数点例外のセマンティクスを有効にします。

例外的な浮動小数点、特定の条件、ゼロ除算などには、FPU は、ハードウェア例外を示す可能性があります。 浮動小数点の例外は、既定で無効にします。 FPU 制御ワードを変更することで、浮動小数点例外が有効になっている、`_controlfp`関数。 たとえば、次のコードは、0 除算の浮動小数点例外を有効にします。

```cpp
_clearfp(); // always call _clearfp before
            // enabling/unmasking a FPU exception
_controlfp( _EM_ZERODIVIDE, _MCW_EM );
```

0 除算の例外が有効になっているときに、分母を 0 と等しい、除算演算シグナル状態になる FPU 例外が発生します。

既定のモードには、FPU 制御ワードを復元するには、呼び出す`_controlfp(_CW_DEFAULT, ~0)`です。

浮動小数点例外のセマンティクスと有効にすると、 **/fp: を除く**フラグは、浮動小数点例外を有効にすると同じではありません。 浮動小数点例外のセマンティクスが有効な場合、コンパイラ必要があります、浮動小数点演算例外をスローする可能性を考慮します。 FPU は別々 のプロセッサ単位であるため、他の単位で指示と同時に、FPU で実行されている手順を実行できます。

浮動小数点例外を有効にすると、FPU は害のある命令の実行を停止し、FPU ステータス ワードを設定して例外条件を通知します。 CPU には、次の浮動小数点命令に達すると、保留中 FPU 例外の最初を確認します。 保留中に例外が、オペレーティング システムによって提供される例外ハンドラーを呼び出すことによって、プロセッサ トラップします。 これは、浮動小数点演算には、例外的な条件が検出されると、対応する例外は検出されません [次へ] の浮動小数点演算が実行されるまでを意味します。 たとえば、次のコードは、0 除算の例外をトラップします。

```cpp
double a, b, c;
// . . .
// ...unmasking of FPU exceptions omitted...
__try
{
   b/c; // assume c==0.0
   printf("This line shouldn't be reached when c==0.0\n");
   c = 2.0*b;
}
__except( EXCEPTION_EXECUTE_HANDLER )
{
   printf("SEH Exception Detected\n");
}
// . . .
```

式で 0 除算の条件が発生したかどうかは、= b または c、FPU されませんトラップ、または raise 式 2.0 で [次へ] の浮動小数点演算まで例外 * b します。 これは、次の出力になります。

```Output
This line shouldn't be reached when c==0.0
SEH Exception Detected
```

Printf 関数の出力の最初の行に対応する必要がありますいないに達しています。式 b/c による浮動小数点の例外が発生した場合に実行が 2.0 に到達するまでに達したが * b します。 B と c の実行後に例外を発生させるには、コンパイラは、"wait"命令を導入する必要があります。

```cpp
// . . .
   __try
   {
      b/c; // assume this expression will cause a "divide-by-zero" exception
      __asm fwait;
      printf("This line shouldn't be reached when c==0.0\n");
      c = 2.0*b;
   }
// . . .
```

この「待機」命令は、FPU の状態と同期され、保留中の例外を処理するプロセッサを強制します。 コンパイラはこれらの生成のみ「待機」指示浮動小数点のセマンティクスが有効にするとします。 これらのセマンティクスが無効な場合、既定では、プログラムが同期にエラーが発生、上記のような浮動小数点例外を使用しています。

浮動小数点のセマンティクスが有効な場合、コンパイラはのみされていない"wait"手順、コンパイラによる不正に使用できる例外が存在する場合、浮動小数点コードを最適化もできなくなります。 これには、例外がスローされたポイントを変更するすべての変換が含まれます。 これらの要因により浮動小数点のセマンティクスを有効にすることがありますかなりの効率が低下アプリケーションのパフォーマンスの低下につながる生成されたマシン語コード。

既定では、fp 浮動小数点例外のセマンティクスが有効になっている: 厳格モードです。 Fp でこれらのセマンティクスを有効にする: 正確なモードでは、追加、 **/fp: を除く**コマンド ライン コンパイラに切り替えます。 浮動小数点例外のセマンティクスも有効になっているし、を使用して、関数によってごとに無効になっている、`float_control`プラグマ。

### <a name="floating-point-exceptions-as-c-exceptions"></a>C++ の例外として、浮動小数点例外

同様、すべてのハードウェア例外浮動小数点例外本質的に、C++ 例外を発生しませんが、代わりに構造化例外をトリガーします。 C++ 例外には、浮動小数点の構造化例外をマップするには、ユーザーは、カスタムの SEH 例外トランスレーターを導入できます。 最初に、各浮動小数点の例外に対応する、C++ 例外を導入します。

```cpp
class float_exception : public std::exception {};

class fe_denormal_operand : public float_exception {};
class fe_divide_by_zero : public float_exception {};
class fe_inexact_result : public float_exception {};
class fe_invalid_operation : public float_exception {};
class fe_overflow : public float_exception {};
class fe_stack_check : public float_exception {};
class fe_underflow : public float_exception {};
```

次に、浮動小数点の SEH 例外を検出し、対応する C++ 例外をスローする変換関数を紹介します。 この関数を使用する、現在のプロセス スレッドで構造化例外ハンドラー トランスレーターを設定、 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) 、ランタイム ライブラリから関数。

```cpp
void se_fe_trans_func( unsigned int u, EXCEPTION_POINTERS* pExp )
{
    switch (u)
    {
    case STATUS_FLOAT_DENORMAL_OPERAND:   throw fe_denormal_operand();
    case STATUS_FLOAT_DIVIDE_BY_ZERO:     throw fe_divide_by_zero();
   etc...
    };
}
// . . .
_set_se_translator(se_fe_trans_func);
```

このマッピングが初期化されると、浮動小数点の例外は、C++ 例外のように動作します。 例えば:

```cpp
try
{
   // floating-point code that might throw divide-by-zero
   // or other floating-point exception
}
catch(fe_divide_by_zero)
{
    cout << "fe_divide_by_zero exception detected" << endl;
}
catch(float_exception)
{
    cout << "float_exception exception detected" << endl;
}
```

## <a name="references"></a>参照

[すべてのコンピューター科学者がについて知って浮動小数点演算](http://pages.cs.wisc.edu/~david/courses/cs552/S12/handouts/goldberg-floating-point.pdf)David 潔でします。

## <a name="see-also"></a>関連項目

[コードの最適化](optimizing-your-code.md)<br/>

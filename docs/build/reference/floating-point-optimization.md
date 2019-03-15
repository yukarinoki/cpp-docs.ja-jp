---
title: MSVC 浮動小数点の最適化
ms.date: 03/09/2018
ms.topic: conceptual
ms.openlocfilehash: 78c5c310f2f348b5cfa5a92feb65e265d28560d9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814372"
---
# <a name="microsoft-visual-c-floating-point-optimization"></a>Microsoft Visual C 浮動小数点の最適化

Microsoft C コンパイラの浮動小数点のセマンティクスを管理する方法を使用してコードを浮動小数点の最適化にハンドルを取得します。 浮動小数点コードで唯一の安全な最適化が実行されるようにしながら高速なプログラムを作成します。

## <a name="optimization-of-floating-point-code-in-c"></a>C++ での浮動小数点コードの最適化

最適化の C++ コンパイラは、マシン コードにソース コードを変換するだけでなく、効率の向上やサイズを小さくように命令を整列します。 残念ながら、多くの一般的な最適化では、浮動小数点計算に適用すると、必ずしも安全されません。 このよい例は、David されるとおりに"何すべてコンピューター科学者必要があります知るの浮動小数点演算"から取得した次の集計アルゴリズムで確認できます*コンピューティング Surveys*、年 3 月 1991 年、pg します。 203:

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

この関数は、n を追加します。 **float**配列のベクトル内の値`A`します。 ループの本体では、アルゴリズムは、合計の次の手順には適用し、「補正」値を計算します。 このメソッドは、累積的なエラーの丸め o (n) 時間の複雑さを維持したままの単純な合計と比較して大幅に減ります。

単純な C++ コンパイラは、浮動小数点演算の実数値の算術演算と同じ代数的な規則に従うことを想定しています可能性があります。 このようなコンパイラが、誤ってという結論を下す

> C = T - sum - Y ==> (sum+Y)-sum-Y ==> 0;

つまり、C の知覚価値が定数 0 では常にします。 この定数値が後続の式に反映し、ループの本体が単純な合計に減少します。 正確には、

> Y = A[i] - C ==> Y = A[i]<br/>T = sum + Y ==> T = sum + A[i]<br/>sum = T ==> sum = sum + A[i]

したがって、単純なコンパイラの論理の変換に、`KahanSum`関数になります。

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0; // C, Y & T are now unused
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

変換されたアルゴリズムは高速化、*を正確に表した、プログラマの意図のではまったくありません*します。 慎重に作成されたエラーの修正が完全に削除され、せようとする、関連付けられているすべてのエラーでシンプルで直接合計アルゴリズム。

コースの高度な C++ コンパイラはその代数認識ルール実際の算術演算は一般には適用されません浮動小数点演算。 ただし、高度な C++ コンパイラも可能性がありますが正しく解釈されない、プログラマの意図。

"(呼び出されたレジスタ格納値) を可能なレジスタに同数の値を保持しようとする一般的な最適化を検討してください。 `KahanSum`例では、この最適化を試みるランタイム変数`C`、`Y`と`T`ループ本体でのみ使用されるため、します。 登録の有効桁数が 23bits (単一) ではなく (double) 52bits の場合は、この最適化効果的に型を昇格させます`C`、`Y`と`T`入力**二重**します。 Sum 変数が同様にレジスタでない場合は、単精度でエンコードされたが残ります。 これは変換のセマンティクス`KahanSum`以下

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

`Y`、`T`と`C`内の値に応じて、正確さに欠ける結果が生じるこのエンコード高い精度では、計算は今すぐ`A[]`します。 したがっても一見無害な最適化があります悪影響が生じる。

この種の最適化の問題は、「厄介」浮動小数点コードに制限はありません。 単純な浮動小数点のアルゴリズムは、適切に最適化されたときに失敗します。 シンプルで直接合計アルゴリズムを検討してください。

```cpp
float Sum( const float A[], int n )
{
   float sum=0;
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

浮動小数点ユニットをいくつかが同時に複数の操作を実行できるため、コンパイラはスカラー リダクション最適化に参加することもできます。 この最適化は、次のように、上記の単純な Sum 関数を効果的に変換します。

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

関数には、各ステップで同時に処理できる 4 つの個別の総和ここでは保持します。 最適化された関数ははるかに高速ようになりましたが、最適化された結果が最適化されていない結果とは大きく異なるできます。 この変更で、コンパイラは浮動小数点加算の連想; と見なされますつまり、これら 2 つの式と同じですが。`(a + b) + c == a + (b + c)`します。 ただし、結合規則は常に当てはまりませんの浮動小数点数。 代わりとして合計を計算します。

```cpp
sum = A[0]+A[1]+A[2]+...+A[n-1];
```

変換の関数は、結果としてを計算するようになりました

```cpp
sum = (A[0]+A[4]+A[8]+...)
    + (A[1]+A[5]+A[9]+...)
    + (A[2]+A[6]+A[10]+...)
    + (A[3]+A[7]+A[11]+...);
```

値によって`A[]`、予期しない結果が生じる加算操作のさまざまなこの注文します。 さらに複雑なことをプログラマによってこのような最適化を予測し、それらを適切に補正できます。 この場合、プログラムは、配列を構築できます`A`は異なる順序で最適化の合計が期待どおりの結果を生成できるようにします。 さらに、多くの状況で最適化された結果の精度は「終了のに十分な」にあります。 これは、最適化が速度の説得力のある利点を提供する場合に特に当てはまります。 ビデオ ゲームには、できるだけはるかに高速化が高精度の浮動小数点演算を必要としない多くの場合、たとえばが必要です。 コンパイラの作成者は、プログラマの速度と精度の多くの場合、さまざまな目標を制御するためのメカニズムしたがってを提供する必要があります。

一部のコンパイラでは、最適化の種類ごとに個別のスイッチを提供することで速度と精度のトレードオフを解決します。 これにより、開発者は、特定のアプリケーションの浮動小数点精度の変更が原因となっている最適化を無効にできます。 このソリューションには、制御、コンパイラの高度な可能性があります提供して、他のいくつかの問題が導入されています。

- 明確ではありません多くの場合、有効または無効にするスイッチです。
- 任意の 1 つの最適化を無効にすると、非浮動小数点コードのパフォーマンスが低下する可能性があります。
- 各追加のスイッチが多く新しいスイッチの組み合わせ。すばやく組み合わせの数は、扱いにくくなります。

最適化ごとの個別のスイッチを提供するように見えますが魅力的なこのようなコンパイラを使用することが煩雑かつ信頼性の低い。

多くの C++ コンパイラを提供、*整合性*浮動小数点モデルは、(を通じて、 **/Op**または **/fltconsistency**スイッチ) 準拠のプログラムを作成する開発者に使用します。厳密な浮動小数点セマンティクスです。 、関与している場合このモデルにより、コンパイラ非浮動小数点コードをこれらの最適化しながら、浮動小数点演算でほとんどの最適化を使用できません。 整合性モデルには、ダーク側ただしがあります。 異なる FPU アーキテクチャのほぼすべての実装で予測可能な結果を返すために **/Op**ラウンドの中間式をユーザーに指定された有効桁数。 たとえば、次の式。

```cpp
float a, b, c, d, e;
// . . .
a = b * c + d * e;
```

一貫性のある反復可能な結果を生成するために **/Op**、次のように実装された場合に、この式は評価を取得します。

```cpp
float x = b  *c;
float y = d * e;
a = x + y;
```

単精度の丸めエラーが発生、最終結果*式の評価では、各ステップで*します。 ただし、この解釈では、C++ のセマンティクスの規則が違反厳密には、浮動小数点式を評価する最良の方法ではほとんどありません。 一般に、中間結果を得るには実用的では、有効桁数として高を計算するより望ましくなります。 式を計算する方がよい、なります`a = b * c + d * e`より高い精度

```cpp
double x = b * c;
double y = d * e;
double z = x + y;
a = (float)z;
```

または、さらには

```cpp
long double x = b * c;
long double y = d * e
long double z = x + y;
a = (float)z;
```

高い有効桁数で中間結果を計算するときに、最終的な結果は大幅に正確です。 皮肉にも、整合性モデルを採用することによりエラーが発生する可能性が向上、ユーザーが安全でない最適化を無効にしてエラーを削減しようと正確にします。 そのため整合性モデルが大幅に低下効率精度向上の保証が同時に提供しないときにします。 重大な数値のプログラマには、これは非常に良好なトレードオフのように思えません、主な理由が、モデルは、一般にも受信していないことです。

以降では、バージョン 8.0 (C++® 2005 年)、Microsoft C コンパイラは、はるかに優れたアプローチを提供します。 これにより、次の 3 つの一般的な浮動小数点モードのいずれかを選択する: fp:/fp:fast 正確であり、fp: 厳密な。

- Fp: 正確には、安全な最適化のみに浮動小数点コードは、実行とは異なり **/Op**、最高の実用的な有効桁数で中間の計算が実行される一貫した方法。
- /fp:fast モードでは、精度と引き換えよりアグレッシブな最適化を許可する浮動小数点の規則を緩和します。
- fp: 厳格モードは fp のすべての一般的な正確性を提供します。 fp 例外のセマンティクスを有効にすると、FPU 環境の変更 (例: 登録精度、丸めの方向などへの変更) が存在する場合、無効な変換を回避しながら正確です。

浮動小数点例外のセマンティクス制御できます別にコマンド ライン スイッチまたはコンパイラのプラグマ; のいずれかによって既定では、浮動小数点例外のセマンティクスは fp の下で無効になっています: 正確かつ fp で有効になっている: 厳密な。 コンパイラでは、FPU 環境と小文字の区別とし、短縮形など特定浮動小数点固有の最適化を制御も提供します。 この単純なモデルは、開発者がさまざまな浮動小数点コードが多すぎるのコンパイラ スイッチの負担や望ましくない副作用の取引関係なしのコンパイルを制御できます。

## <a name="the-fpprecise-mode-for-floating-point-semantics"></a>Fp: 浮動小数点のセマンティクスのための正確なモード

既定の浮動小数点セマンティクス モードは fp のです。 正確な。 このモードがオンの場合、コンパイラ厳密に従ったセーフの規則群に浮動小数点演算を最適化するときにします。 これらの規則には、浮動小数点演算の精度を維持しながら、効率的なマシン コードを生成するコンパイラが許可されます。 高速の運用を容易にするプログラムは、fp: 正確なモデル (ただし、これらは明示的に有効にする) の浮動小数点例外のセマンティクスを無効にします。 Microsoft が fp を選択: 迅速かつ正確な両方のプログラムを作成するため、既定の浮動小数点モードとして正確です。

Fp を明示的に要求する: precise モードを使用して、コマンド ライン コンパイラを使用して、 [/fp: 正確な](fp-specify-floating-point-behavior.md)スイッチします。

> cl /fp:precise source.cpp

これは、ように fp を使用するコンパイラに指示: source.cpp ファイルのコードを生成するときに、正確なセマンティクスです。 Fp: 正確なモデルを使用して、関数ごとに呼び出すこともできます、 [float_control コンパイラのプラグマ](#the-float-control-pragma)します。

Fp: precise モードは、コンパイラは決して摂浮動小数点演算の精度を最適化を実行します。 コンパイラの割り当てで正しく丸め常には、丸めないおよび関数呼び出し、され中間丸め処理を行う一貫した方法が実行されます、同一有効桁数で、FPU の登録とします。 既定では、し、短縮形などの安全な最適化が有効にします。 既定では、セマンティクスの例外および FPU 環境と小文字の区別が無効になります。

|fp: 正確なセマンティクス|説明|
|-|-|
|丸めセマンティクス|割り当てに明示的な丸めタイプにキャストし、関数を呼び出します。 登録の有効桁数で中間式が評価されます。|
|代数変換|非結合、非分散の浮動小数点代数に厳密な準拠している変換が常に保証する場合を除き、同じ結果を生成します。|
|短縮形|既定で許可されています。 詳細については、セクションを参照してください。 [fp_contract プラグマ](#the-fp-contract-pragma)します。|
|浮動小数点の評価の順序|最終的な結果が改ざんされていないこと、コンパイラは浮動小数点式の評価を並べ替えることがあります。|
|FPU 環境のアクセス|既定で無効になっています。 詳細については、セクションを参照してください。 [fenv_access プラグマ](#the-fenv-access-pragma)します。 既定の有効桁数と丸めモードと見なされます。|
|浮動小数点例外のセマンティクス|既定で無効になっています。 詳細については、次を参照してください。 [/fp: 除く](fp-specify-floating-point-behavior.md)します。|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpprecise"></a>Fp 浮動小数点式のセマンティクスの丸め: 正確な

Fp: 正確なモデルが常に最高の実用的な精度、丸め処理を式の評価で特定の時点でのみ明示的に行うで中間の計算を実行します。 常にユーザーが指定した有効桁数に丸め処理を行う 4 つの場所で発生します (a) 割り当てが行われると、(b)、型キャストが実行されると、(c) 浮動小数点値が渡された場合、引数として関数から浮動小数点値が返される場合 (d) を、。関数。 中間結果の精度はプラットフォームによって異なります、中間の計算は、登録の有効桁数で常に実行される、ためです (有効桁数が指定されたユーザーとして少なくとも正確では常に、有効桁数)。

次のコードの代入式を検討してください。 代入演算子の '=' の右辺の式は登録の有効桁数で計算し、代入の左辺の型に明示的に丸めなります。

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

中間結果を明示的に丸める、型キャストを紹介します。 たとえば、追加することで、前のコードが変更された場合、明示的な型キャスト、中間式 (c * d) は、型キャストの型に丸められます。

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

この丸め処理を行うメソッドの 1 つの意味は、一部一見同等の変換は同じ意味で実際にはありません。 たとえば、次の変換は、2 つの割り当て式に 1 つの代入式を分割します。

```cpp
float a, b, c, d;
// . . .
a = b*(c+d);
```

ないと同じです

```cpp
float a, b, c, d;
// . . .
a = c+d;
a = b*a;
```

同様に。

```cpp
a = b*(c+d);
```

ないと同じです

```cpp
a = b*(a=c+d);
```

これらのエンコーディングは、それぞれの 2 つ目のエンコーディングが追加の代入演算を導入していますが、そのため、ポイント、丸め処理と同じセマンティクスがありません。

関数には、浮動小数点値が返される、ときに、関数の型に値が丸められます。 浮動小数点値は、関数にパラメーターとして渡される、値は、パラメーターの型に丸められます。 例えば:

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

同様に。

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

### <a name="architecture-specific-rounding-under-fpprecise"></a>Fp で丸め処理アーキテクチャに固有: 正確な

|プロセッサ|中間式の有効桁数を丸め処理|
|-|-|
|x86|中間式は、16 ビットの指数部によって提供される拡張の範囲と 53 ビットの既定の精度で計算されます。 これらの 53:16 値は、(関数の呼び出し中に発生することができます) としてメモリに「あふれた」は、ときに、11 ビットに拡張の指数の範囲に絞り込まれます。 つまり、書き込まれた値は、11 ビット指数のみでの倍精度の標準形式にキャストされます。<br/>ユーザーは、拡張の 64 ビット精度浮動小数点制御ワードを使用して、変更することによって、中間丸め処理に切り替えることがあります`_controlfp`および FPU 環境のアクセスを有効にすると (を参照してください[fenv_access プラグマ](#the-fenv-access-pragma))。 ただし、メモリには、拡張精度レジスタの値が書き込まれた、ときに、中間結果が倍精度にまだ丸められます。<br/>この特定のセマンティクスは変更されます。|
|amd64|Amd64 の FP セマンティクスは少し異なるその他のプラットフォームです。 パフォーマンス向上のための中間操作の代わりに、最も広いの有効桁数でのいずれかのオペランドの最も有効桁数で計算されます。  オペランドよりも広いの有効桁数を使用して計算する計算を強制するには、ユーザーはサブ式の少なくとも 1 つのオペランドでキャスト操作を導入する必要があります。<br/>この特定のセマンティクスは変更されます。|

### <a name="algebraic-transformations-under-fpprecise"></a>代数変換 fp: 正確な

ときに、fp: precise モードが有効になっている、コンパイラは代数変換を実行しない*最終的な結果がおそらくと同一でない限り*します。 実数値の算術演算の使い慣れた代数のルールの多くは浮動小数点演算は常に保持されません。 たとえば、次の式は同等のレアル、必ずしも浮動小数点数の。

|フォーム|説明|
|-|-|
|`(a+b)+c = a+(b+c)`|追加の結合規則|
|`(a*b)*c = a*(b*c)`|乗算の結合規則|
|`a*(b+c) = a*b + b*c`|に対する乗算の配布|
|`(a+b)(a-b) = a*a-b*b`|代数のファクタリング|
|`a/b = a*(1/b)`|逆数で除算しました。|
|`a*1.0 = a`|乗法|

関数の概要の例に示すように`KahanSum`コンパイラはかなり高速のプログラムを生成するためにさまざまな代数変換を実行するよ可能性があります。 このような代数変換に依存する最適化がほぼ常に正しくないためには完全に安全な場合は。 たとえば、除算を置き換えることが望ましい場合があります、*定数*定数の乗法逆関数での乗算値。

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

これは、オプティマイザーはコンパイル時にその x に判断できるための安全な変換/4.0 のすべての浮動小数点値 x、無限大および NaN を含む x*(1/4.0) = =。 乗算と除算演算を置き換えることで、コンパイラがいくつかのサイクルを節約できます: 特に、除算を直接実装はありませんが、コンパイラが逆数近似の組み合わせを生成して、積和演算を必要とする FPUs で手順です。 コンパイラは fp の下で、このような最適化を実行できます。 正確な置換乗算生成、正確な場合にのみ同じ結果になります、除算として。 コンパイラは fp の下の単純な変換も実行できます。 正確な結果が同じです。 不足している機能には次が含まれます。

|フォーム|説明
|-|-|
|`(a+b) == (b+a)`|追加するための可換性ルール|
|`(a*b) == (b*a)`|乗算の可換性ルール|
|`1.0*x*y == x*1.0*y == x*y*1.0 == x*y`|1.0 による乗算|
|`x/1.0*y == x*y/1.0 == x*y`|1.0 での除算|
|`2.0*x == x+x`|2.0 での乗算|

### <a name="contractions-under-fpprecise"></a>短縮形 fp: 正確な

多くの最新の浮動小数点ユニットの重要なアーキテクチャの機能は、中間丸めエラーに 1 回の操作の追加後に乗算を実行する機能です。 Intel Itanium アーキテクチャが各三項操作、結合する手順を提供するなど、(、*b + c)、(、* b c) と (c、* b)、1 つの浮動小数点命令に (fma、fms と fnma それぞれ)。 1 つの手順は、乗算し、追加の手順については、個別に実行するよりも高速より正確な製品の中間丸め処理がないためです。 この最適化は大幅に高速化する関数のインターリーブを乗算していくつか含むし、操作を追加します。 たとえば、次の 2 つの n 次元ベクトルのドット積を計算するアルゴリズムを検討してください。

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

この計算を実行できる一連の乗算の追加手順については、フォーム p の = p + x [i] * y [i]。

省略形の最適化できますが個別に制御を使用して、`fp_contract`コンパイラのプラグマ。 既定では、fp: 処理速度と精度を向上するための短縮により、正確なモデルです。 Fp: 正確には、コンパイラは縮小しない明示的な丸めを適用した式。
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

浮動小数点式の評価の順序を維持するための最適化は常に安全と fp のため許可: precise モード。 単精度の 2 つの n 次元ベクトルのドット積を計算する次の関数を検討してください。 最初のコード ブロックは、元の関数ように、プログラマによってエンコードする必要があります、同じ関数に続けて部分のループ アンローリングの最適化。

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

この最適化の主な利点は、ループ条件付き分岐の数は 75% が減ることです。 また、ループ本体内の操作の数を増やすと、コンパイラようになりましたがありますをさらに最適化する機会が多く。 たとえば、いくつか FPUs を実行することができます、p + = 積和 x [i] * y [i] x [i + 1] の値を同時にフェッチ中に、y [i + 1]、次の手順で使用します。 この種類の最適化は、操作の順序を保持するのでに浮動小数点演算を完全にも安全です。

コンパイラが高速なコードを生成するには全体の操作の順序を変更すると便利です。 次のコードがあるとします。

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

C++ の意味ルールを示す、最初に計算された場合と、プログラムに結果を生成する必要があります、x、y、最後に z。 コンパイラが使用可能な浮動小数点レジスタを 4 つだけあるとします。 計算する、コンパイラが強制された場合 x、y、z 順セマンティクスは次のコードを生成することを選択します。

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

いくつか明らかに重複した操作では、このエンコーディングがあります。 コンパイラは、C++ の意味ルールを厳密に従う場合、この順序付けは必要ためプログラムが各割り当てには中間 FPU 環境のアクセス可能性があります。 ただし、fp の既定の設定: 正確なコンパイラは、プログラムは、環境へのアクセスのように最適化するためにこれらの式の順序を変更できるようにします。 逆の順序で、次のように、3 つの値を計算することによって、重複を削除する無料されます。

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

このエンコードは、約 40% 削減 fp 命令の数が、明確に優れたです。 結果の x、y と z は同じと同様に、少ないオーバーヘッドで計算が。

Fp: 正確には、コンパイラも*インター レース*高速なコードを生成するための共通のサブ式。 たとえば、としては、次のように、二次方程式のルートを計算するコードを記述する場合があります。

```cpp
double a, b, c, root0, root1;
...
root0 = (-b + sqrt(b*b-4*a*c))/(2*a);
root1 = (-b - sqrt(b*b-4*a*c))/(2*a);
```

これらの式は、1 つの操作によってのみ異なりますが、プログラマが記述したルートの各値が最高の実用的な精度で計算することを保証するには、この方法。 Fp: コンパイラは自由 root0 と有効桁数を失うことがなく、共通のサブ式を削除する root1 の計算をインター レースに正確には、します。 たとえば、次が削除余分な手順がいくつか正確な同じ回答を生成中に。

```cpp
double a, b, c, root0, root1;
...
register tmp0 = -b;
register tmp1 = sqrt(b*b-4*a*c);
register tmp2 = 2*a;
root0 = (tmp0+tmp1)/tmp2;
root1 = (tmp0-tmp1)/tmp2;
```

その他の最適化は、特定の独立した式の評価を移動しようとする可能性があります。 条件付き分岐、ループ本体の内部を含む、次のアルゴリズムを検討してください。

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

コンパイラはそれを検出可能性があります、式の値 (abs(d) > 1) はループ本体の内部バリアントではありません。 これにより、コンパイラを「行う」場合は、次のように、上記のコードを変換する、ループ本体の外側のステートメント。

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

変換後が不要になった条件分岐のため、ループの全体的なパフォーマンスを大幅に向上、ループ本体のいずれか。 この種類の最適化が完全に安全なため、式の評価 (abs(d) > 1.0) は他の式に依存しません。

FPU 環境のアクセス、浮動小数点例外が存在する場合は、セマンティックのフローが変更されるため、これらの種類の最適化は contraindicated します。 このような最適化は fp で使用可能なのみ: precise モード FPU 環境のアクセスと浮動小数点例外のセマンティクスは既定で無効になっています。 FPU 環境にアクセスする関数できますを使用してこのような最適化を明示的に無効化、`fenv_access`コンパイラのプラグマ。 同様に、浮動小数点例外を使用して関数を使用する必要があります、`float_control(except ... )`コンパイラのプラグマ (またはを使用して、 **/fp: 除く**コマンド ライン スイッチ)。

要約すると、fp: 正確なモードでは、コンパイラは最終的な結果が改ざんされていないことを条件に浮動小数点式の評価の順序を変更して、結果は、依存関係にある、FPU 環境または浮動小数点例外ではありません。

### <a name="fpu-environment-access-under-fpprecise"></a>FPU environment access under fp:precise

ときに、fp: precise モードが有効な場合、コンパイラは、プログラムのアクセスまたは FPU 環境の変更はありません。 前述のように、この前提により、コンパイラの順序を変更または移動 fp の下の効率を向上させるために浮動小数点演算に: 正確です。

一部のプログラムを使用して浮動小数点丸め方向を変更することがあります、`_controlfp`関数。 たとえば、一部のプログラム コンピューティング上と、下のエラー境界算術演算で 2 回、同じ計算を実行することによって最初に負の無限大方向に丸め、中に、中に正の無限大方向に丸め処理を行います。 FPU は、丸め処理を制御する便利な手段を提供するため、プログラマの丸めモードを変更するには、FPU 環境を変えることができます。 次のコードでは、FPU 環境を変更することにより、正確なエラーが浮動小数点の乗算のバインドを計算します。

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -&infin;
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );    // round to +&infin;
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

Fp : 正確には、常と見なされます、既定の FPU 環境、オプティマイザーが無料への呼び出しを無視するように`_controlfp`cUpper に上記の割り当てを減らすと cLower を = =、* b; 正しくない結果が得これが明確にします。 このような最適化を防ぐためには、使用して、FPU 環境のアクセスを有効に、`fenv_access`コンパイラのプラグマ。

その他のプログラムは、FPU のステータス ワードをチェックして特定の浮動小数点エラーを検出しようとします。 たとえば、0 除算と不正確な条件の次のコードを確認します

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

Fp: 正確には、式の評価の順序を変更する最適化は特定のエラーが発生するポイントを変更できます。 ステータス ワードにアクセスするプログラムを使用して FPU 環境のアクセスを有効にする必要があります、`fenv_access`コンパイラのプラグマ。

詳細については、セクションを参照してください。 [fenv_access プラグマ](#the-fenv-access-pragma)します。

### <a name="floating-point-exception-semantics-under-fpprecise"></a>Fp 浮動小数点例外のセマンティクス: 正確な

既定では、浮動小数点例外のセマンティクスは fp の下で無効になっています。 正確な。 C++ プログラマのほとんどは、システムまたは C++ の例外を使用せず、浮動小数点の例外的な条件を処理するために優先します。 さらに、前述のように、浮動小数点例外のセマンティクスを無効にすると、コンパイラより柔軟に浮動小数点演算を最適化するときにできます。 いずれかを使用して、 **/fp: を除く**スイッチまたは`float_control`fp を使用する場合は、浮動小数点例外のセマンティクスを有効にするプラグマ: 正確なモデルです。

詳細については、セクションを参照してください。[浮動小数点例外のセマンティクスを有効にする](#enabling-floating-point-exception-semantics)します。

## <a name="the-fpfast-mode-for-floating-point-semantics"></a>浮動小数点のセマンティクスの/fp:fast モード

コンパイラがその fp について、規則を緩和して/fp:fast モードが有効にすると: 浮動小数点演算を最適化するときに正確に使用します。 このモードは、浮動小数点の精度と正確性の速度の浮動小数点コードをさらに最適化するためにコンパイラを使用します。 正確な浮動小数点計算に依存しないプログラム/fp:fast モードを有効にすると、速度が大幅に向上があります。

/Fp:fast 浮動小数点モードが有効な場合を使用して、 [/fp:fast](fp-specify-floating-point-behavior.md)次のようにコマンド ライン コンパイラ スイッチ。

> cl/fp:fast source.cpp

この例では、コンパイラ source.cpp ファイルのコードを生成するときに、/fp:fast セマンティクスを使用するように指示します。 /Fp:fast モデルを使用して、関数ごとに呼び出すこともできます、`float_control`コンパイラのプラグマ。

詳細については、セクションを参照してください。 [float_control プラグマ](#the-float-control-pragma)します。

/Fp:fast モードの場合、コンパイラは浮動小数点演算の精度を変更する最適化を実行可能性があります。 コンパイラの割り当てで正しく丸め可能性があります、丸めないまたは関数呼び出し、および中間丸め処理は常に実行されません。 短縮形など、特定浮動小数点の最適化は常に有効にします。 セマンティクスの浮動小数点例外および FPU 環境と小文字の区別は、無効になっており、使用できません。

|/fp:fast セマンティクス|説明
|-|-|
|丸めセマンティクス|割り当て、明示的な丸め処理を丸めない、および関数呼び出しを無視する場合があります。<br/>中間式は、登録のパフォーマンスの要件に従って有効桁数未満に丸められます可能性があります。|
|代数変換|コンパイラが式に従って実数値連想、詞代数; を変換可能性があります。これらの変換は、正確なまたは適切な保証はありません。|
|短縮形|常に有効にします。プラグマで無効にすることはできません。 `fp_contract`|
|浮動小数点の評価の順序|このような変更が最終的な結果を変更する場合でも、コンパイラは、浮動小数点式の評価を並べ替えることがあります。|
|FPU 環境のアクセス|無効になります。 使用できません|
|浮動小数点例外のセマンティクス|無効になります。 使用できません|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpfast"></a>/Fp:fast 浮動小数点式のセマンティクスの丸め処理を行う

Fp とは異なり:/fp:fast モデルの正確なモデルは、最も便利な有効桁数の中間の計算を実行します。 丸めないに割り当て、丸め処理を行うと、関数呼び出しには常には発生しません。 下の最初の関数が単精度の 3 つの変数を導入する、(`C`、`Y`と`T`)。 コンパイラは可能性がありますランタイム型の昇格の有効なこれらの変数に選択`C`、`Y`と`T`倍精度にします。

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

変数のレジスタ格納:

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

この例で/fp:fast は元の関数の目的をならない点です。 最終的な最適化の結果を変数に保持されている`sum`、正しい結果から非常に不安になる場合があります。

/Fp:fast、下、コンパイラは、少なくとも、ソース コードで指定された有効桁数を維持するために通常試みます。 ただし、場合によっては、コンパイラを選択できますで中間式を実行する、*精度を下げる*ソース コードで指定します。 たとえば、最初のコード ブロックは、平方根関数の倍精度のバージョンを呼び出します。 倍精度の呼び出しに置換する結果と、関数のオペランドが明示的にキャストするとき、単精度などの特定の状況で、/fp:fast 下コンパイラこともできます`sqrt`単精度への呼び出しで`sqrtf`関数。 キャストを確実に入る値ため`sqrt`と出力されている値は 1 つの有効桁数に丸められます、丸め処理の代わりにのみ変更します。 Sqrt に送信される値が倍精度値と、コンパイラは、この変換を実行、有効桁数のビットの半分ほどが正しくない可能性があります。

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

ただし、正確性この最適化は、特に有益などの関数の組み込みのバージョンの単精度を提供するプロセッサを対象とする場合`sqrt`します。 コンパイラがときにこのような最適化に使用がだけ正確には、依存関係にあるプラットフォームとコンテキストの両方です。

さらに、コンパイラに使用可能な有効桁数のレベルで実行できる中間の計算の有効桁数の整合性を確保することはありません。 コンパイラは、少なくとも、コードで指定された精度のレベルを維持する試行は、/fp:fast により、オプティマイザーはダウン キャストの中間の計算をより迅速にまたはより小さいマシン語コードを生成するためにします。 たとえば、コンパイラがいくつかの中間の乗算単精度に丸める上記のコードをさらに最適化することがあります。

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

このような追加の丸めを低い精度浮動小数点ユニット、SSE2 などを使用して中間の計算の一部を実行する可能性があります。 /Fp:fast 丸め処理の精度は、そのためプラットフォームによって異なります。1 つのプロセッサ用にコンパイルするコードは、別のプロセッサに適して必ずしもに機能しない可能性があります。 速度の利点がありますが、精度の問題を上回るかどうかを判断するユーザーをそのままです。

/Fp:fast 最適化が特に問題と、特定の関数の場合は、浮動小数点モード ローカルに切り替えられる fp: 正確なを使用して、`float_control`コンパイラのプラグマ。

### <a name="algebraic-transformations-under-fpfast"></a>/Fp:fast 代数変換

/Fp:fast モードにより、コンパイラが、一部の実行から浮動小数点代数変換が安全でない式をポイントします。 たとえば、安全でない、次の最適化の場合は、/fp:fast 採用されている可能性があります。

||||
|-|-|-|
|元のコード|手順 1.|手順 2
|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = y – a – b;`<br/><br/>`c = x – z;`<br/><br/>`c = x * z;`<br/><br/>`c = x - z;`<br/><br/>`c = x + z;`<br/><br/>`c = z-x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x – 0;`<br/><br/>`c = x * 0;`<br/><br/>`c = x - 0;`<br/><br/>`c = x + 0;`<br/><br/>`c = 0 - x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x;`<br/><br/>`c = 0;`<br/><br/>`c = x;`<br/><br/>`c = x;`<br/><br/>`c = -x;`|

手順 1 で、コンパイラを監視する`z = y – a – b`は常に 0 を等しくします。 これは、無効な監視では技術的には、/fp:fast 下で許可されます。 コンパイラは、変数 z の各後で使用する定数値 0 を伝達します。 手順 2 で、さらに、コンパイラの最適化を監視することで`x - 0 == x`、`x * 0 == 0`など。ここでも、これらの所見が厳密に有効でない場合でもは/fp:fast 下で許可されます。 最適化されたコードでは、はるかに高速になりますが、かなり正確性が低下または誤ったがあります。

/Fp:fast モードが有効にすると、次 (安全でない) 代数のルールのいずれかのオプティマイザーに雇われる可能性があります。

|||
|-|-|
|フォーム|説明|
|`(a + b) + c = a + (b + c)`|追加の結合規則|
|`(a * b) * c = a * (b * c)`|乗算の結合規則|
|`a * (b + c) = a * b + b * c`|に対する乗算の配布|
|`(a + b)(a - b) = a * a - b * b`|代数のファクタリング|
|`a / b = a * (1 / b)`|逆数で除算しました。|
|`a * 1.0 = a, a / 1.0 = a`|乗法|
|`a ± 0.0 = a, 0.0 - a = -a`|加法|
|`a / a = 1.0, a - a = 0.0`|キャンセル|

/Fp:fast 最適化が特定の関数に対して特に問題がある場合は、浮動小数点モード ローカルに切り替えられる fp: 正確なを使用して、`float_control`コンパイラのプラグマ。

### <a name="order-of-floating-point-expression-evaluation-under-fpfast"></a>/Fp:fast 浮動小数点式の評価の順序

Fp とは異なり: 正確には、/fp:fast により、コンパイラは、高速なコードを生成するための浮動小数点演算の順序を変更します。 したがって、/fp:fast でいくつかの最適化では、式の目的の順序が保持されません可能性があります。 たとえば、2 つの n 次元ベクトルのドット積を計算する次の関数を検討してください。

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

オプティマイザー/fp:fast、下のスカラー リダクションを実行できます、`dotProduct`関数、関数を次のように効果的に変換します。

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

最適化されたバージョンの関数で 4 つの個別製品総和に同時に実行し、一緒に追加し、します。 この最適化に高速化を計算する、`dotProduct`よりも少なくして、ターゲット プロセッサが、最終的な結果に応じて 4 つの係数ので不正確であるレンダリング役に立たないか。 このような最適化が特に問題のある 1 つの関数または翻訳単位の場合は、浮動小数点モード ローカルに切り替えられる fp: 正確なを使用して、`float_control`コンパイラのプラグマ。

## <a name="the-fpstrict-mode-for-floating-point-semantics"></a>Fp: 浮動小数点のセマンティクスの厳格モード

ときに、fp: 厳格モードが有効な場合、コンパイラがその fp をすべて同じルールに準拠: 浮動小数点演算を最適化するときに、正確な使用します。 このモードは、浮動小数点例外のセマンティクスと FPU 環境に小文字の区別できるようにもとし、短縮形などの特定の最適化を無効にします。 操作の最も厳格なモードです。

Fp: 厳密な浮動小数点モードが有効な場合を使用して、 [/fp: 厳密な](fp-specify-floating-point-behavior.md)次のようにコマンド ライン コンパイラ スイッチ。

> cl /fp:strict source.cpp

この例のようにコンパイラ fp の使用を: source.cpp ファイルのコードを生成するときに、厳密な型指定します。 Fp: 厳格なモデルを使用して、関数ごとに呼び出すこともできます、`float_control`コンパイラのプラグマ。

詳細については、セクションを参照してください。 [float_control プラグマ](#the-float-control-pragma)します。

Fp: 厳格モードでは、コンパイラは決して摂浮動小数点演算の精度を最適化を実行します。 コンパイラの割り当てで正しく丸め常には、丸めないおよび関数呼び出し、され中間丸め処理を行う一貫した方法が実行されます、同一有効桁数で、FPU の登録とします。 既定では、セマンティクスの浮動小数点例外および FPU 環境と小文字の区別が有効にします。 コンパイラは、すべてのケースで正確性を保証できませんので、し、短縮形などの特定の最適化が無効です。

|fp: 厳密な型指定|説明|
|-|-|
|丸めセマンティクス|割り当て、明示的な丸め処理を丸めない、および関数呼び出し<br/>登録の有効桁数で中間式が評価されます。<br/>Fp と同じです正確な。|
|代数変換|非結合、非分散の浮動小数点代数に厳密な準拠している変換が常に保証する場合を除き、同じ結果を生成します。<br/>Fp と同じです正確な。|
|短縮形|常に無効になっています|
|浮動小数点の評価の順序|コンパイラは浮動小数点式の評価の順序を変更しません|
|FPU 環境のアクセス|常に有効にします。|
|浮動小数点例外のセマンティクス|既定で有効になります。|

### <a name="floating-point-exception-semantics-under-fpstrict"></a>Fp 浮動小数点例外のセマンティクス: strict

既定では、浮動小数点例外のセマンティクスは fp の下で有効になっている: 厳格なモデルです。 このようなセマンティクスを無効にするには、いずれかを使用、 **/fp: 以外の**切り替えるか、導入、`float_control(except, off)`プラグマ。

詳細については、セクションを参照して[浮動小数点例外のセマンティクスを有効にする](#enabling-floating-point-exception-semantics)と[float_control プラグマ](#the-float-control-pragma)します。

## <a name="the-fenvaccess-pragma"></a>Fenv_access プラグマ

使用法:

```cpp
#pragma fenv_access( [ on  | off ] )
```

[Fenv_access](../../preprocessor/fenv-access.md)プラグマは、FPU フラグ テストと FPU モードの変更を妨害する可能性がありますが、特定の最適化コンパイラを使用します。 ときの状態`fenv_access`が無効で、コンパイラは想定できます既定 FPU のモードが有効では、FPU フラグにテストされていません。 Fp の既定では、環境へのアクセスが無効になります: precise モードは、このプラグマを使用してを明示的に有効することもできます。 Fp: strict、`fenv_access`は常に有効し、無効にすることはできません。 /Fp:fast、`fenv_access`は常に無効になり、有効にすることはできません。

Fp」の説明に従って: 正確なセクションは、いくつかのプログラマを使用して浮動小数点丸め方向を変更することが、`_controlfp`関数。 たとえば、算術演算に上限と下限のエラーの境界を計算する一部のプログラム同じ計算を実行 2 回、負の無限大方向に丸め処理中に、まず、正の無限大方向に丸め処理中に。 FPU は、丸め処理を制御する便利な手段を提供するため、プログラマの丸めモードを変更するには、FPU 環境を変えることができます。 次のコードでは、FPU 環境を変更することにより、正確なエラーが浮動小数点の乗算のバインドを計算します。

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -infinity
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );       // round to +infinity
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

無効にすると、`fenv_access`プラグマは、既定の FPU 環境を想定するコンパイラを使用。 そのため、オプティマイザーは無料で呼び出しを無視`_controlfp`に上記の割り当てを減らすと`cUpper = cLower = a*b`します。 ただし、有効にすると`fenv_access`このような最適化を防止します。

プログラムは、特定の浮動小数点エラーを検出するために、FPU ステータス ワードを調べることもできます。 たとえば、0 除算と不正確な条件の次のコードを確認します

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

ときに`fenv_access`は無効にすると、コンパイラは浮動小数点式が、したがっておそらく兼ねてハッキングする. FPU のステータス チェックの実行順序を並べ替える可能性があります。 有効にする`fenv_access`このような最適化を防止します。

## <a name="the-fpcontract-pragma"></a>Fp_contract プラグマ

使用法:

```cpp
#pragma fp_contract( [ on | off ] )
```

Fp」の説明に従って: 正確なセクションを省略形は、多くの最新の浮動小数点ユニットの基本的なアーキテクチャの機能です。 短縮形は、中間丸めエラーに 1 回の操作の追加後に乗算を実行する機能を提供します。 1 つの手順は、乗算し、追加の手順については、個別に実行するよりも高速より正確な製品の中間丸め処理がないためです。 Contracted の操作の値を計算できます`(a*b+c)`と両方の操作か無限の精度を計算が丸め、浮動小数点数に最も近い。 この最適化は大幅に高速化する関数のインターリーブを乗算していくつか含むし、操作を追加します。 たとえば、次の 2 つの n 次元ベクトルのドット積を計算するアルゴリズムを検討してください。

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

この計算を実行できる一連の乗算の追加手順については、フォームの`p = p + x[i]*y[i]`します。

[Fp_contract](../../preprocessor/fp-contract.md)プラグマは、浮動小数点式を縮小できるかどうかを指定します。 既定では、fp: 処理速度と精度を向上するための短縮形 precise モードを使用します。 短縮形は常に、/fp:fast モードを有効にします。 ただし、短縮形は、エラー条件の明示的な検出を覆すことができます、 `fp_contract` fp プラグマが常に無効になっています: 厳格モード。 可能性のある式の例を縮小するときに、`fp_contract`プラグマが有効になっています。

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

**/Fp: 正確な**、 **/fp:fast**、 **/fp: 厳密な**と **/fp: 除く**スイッチは制御ファイルでのファイルの浮動小数点のセマンティクス基準です。 [Float_control](../../preprocessor/float-control.md)プラグマの関数ごとにこのようなコントロールを提供します。

使用法:

```cpp
#pragma float_control(push)
#pragma float_control(pop)
#pragma float_control( precise, on | off [, push] )
#pragma float_control( except, on | off [, push] )
```

プラグマ`float_control(push)`と`float_control(pop)`それぞれをプッシュして、浮動小数点モードと、スタックの例外 オプションの現在の状態をポップします。 注意の状態、`fenv_access`と`fp_contract`プラグマの影響を受けない`pragma float_control(push/pop)`します。

プラグマを呼び出す`float_control(precise, on)`が有効にして`float_control(precise, off)`precise モードのセマンティクスが無効になります。 同様に、プラグマ`float_control(except, on)`が有効にして`float_control(except, off)`例外のセマンティクスが無効になります。 例外のセマンティクスは、正確なセマンティクスも有効になっている場合にのみ有効にできます。 ときに、省略可能な`push`が存在する場合の状態、`float_control`オプションは、セマンティクスを変更する前にプッシュされます。

### <a name="setting-the-floating-point-semantic-mode-on-a-function-by-function-basis"></a>関数ごとに浮動小数点のセマンティックのモードの設定

コマンド ライン スイッチは、実際には、次の 4 つの異なる浮動小数点プラグマの設定の短縮形です。 関数ごとに特定の浮動小数点セマンティック モードを明示的に選択するには、次の表に示す 4 つのオプションの浮動小数点プラグマのそれぞれを選択します。

||||||
|-|-|-|-|-|
||float_control(precise)|float_control(except)|fp_contract|fenv_access|
|/fp:strict|on|on|オフ|on|
|/fp:strict /fp:except-|on|オフ|オフ|on|
|/fp: 正確な|on|オフ|on|オフ|
|/fp:precise /fp:except|on|on|on|オフ|
|/fp:fast|オフ|オフ|on|オフ|

たとえば、次を明示的に有効/fp:fast セマンティクスです。

```cpp
#pragma float_control( except, off )   // disable exception semantics
#pragma float_control( precise, off )  // disable precise semantics
#pragma fp_contract(on)                // enable contractions
#pragma fenv_access(off)               // disable fpu environment sensitivity
```

> [!Note]
> 例外のセマンティクスは、"precise"セマンティクスをオフにする前に、オフにする必要があります。

## <a name="enabling-floating-point-exception-semantics"></a>浮動小数点例外のセマンティクスを有効にします。

0 による除算など特定例外的な浮動小数点の条件には、FPU は、ハードウェア例外を示す可能性があります。 既定では、浮動小数点例外が無効になります。 FPU 制御ワードを変更することで、浮動小数点例外が有効になっている、`_controlfp`関数。 たとえば、次のコードは、0 除算の浮動小数点例外を有効にします。

```cpp
_clearfp(); // always call _clearfp before
            // enabling/unmasking a FPU exception
_controlfp( _EM_ZERODIVIDE, _MCW_EM );
```

0 除算の例外が有効になっているときに、分母が 0 で除算操作がシグナル状態に FPU 例外が発生します。

既定のモードには、FPU 制御ワードを復元するには、呼び出す`_controlfp(_CW_DEFAULT, ~0)`します。

による浮動小数点例外のセマンティクスを有効にすると、 **/fp: 除く**フラグは、浮動小数点例外を有効にすると同じではありません。 浮動小数点例外のセマンティクスを有効にすると、任意の浮動小数点演算が例外をスロー可能性コンパイラを考慮する必要があります。 FPU は別々 のプロセッサ単位であるためと手順については、他の単位は同時 FPU で実行されている手順を実行できます。

浮動小数点例外を有効にすると、FPU が問題のある命令の実行を停止し、FPU のステータス ワードを設定して、例外的な条件を通知します。 CPU では、次の浮動小数点命令に達すると、保留中、FPU 例外をまず確認します。 保留中の例外は、オペレーティング システムによって提供される例外ハンドラーを呼び出すことによって、プロセッサ トラップします。 これは、浮動小数点演算には、例外条件が検出されると、対応する例外はありませんが認識されること、[次へ] の浮動小数点演算が実行されるまでことを意味します。 たとえば、次のコードは、0 除算の例外をトラップします。

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

式で 0 除算の条件が発生したかどうか、b と c = FPU しませんトラップ、または raise 式 2.0 で [次へ] の浮動小数点演算まで例外 * b。 これは、次の出力が得られます。

```Output
This line shouldn't be reached when c==0.0
SEH Exception Detected
```

Printf 関数の出力の最初の行に対応する必要がありますが達していない;実行 2.0 に到達するまで、式 b/c による浮動小数点例外が発生したために達したが * b。 B と c の実行後に例外を発生させるには、コンパイラは、「待機」命令を導入する必要があります。

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

この「待機」命令では、FPU の状態と同期し、保留中の例外を処理するプロセッサを強制します。 コンパイラはこれらの生成のみ「待機」手順浮動小数点セマンティクスが有効にするとします。 このようなセマンティクスを無効に既定では、プログラムで浮動小数点例外を使用する場合に、上記のような同期エラーが発生可能性があります。

浮動小数点セマンティクスが有効な場合、コンパイラでは「待機」手順がのみ紹介できません、コンパイラから不正に可能性のある例外が存在する場合、浮動小数点コードを最適化することもできなくなります。 これには、例外がスローされたポイントを変更する変換が含まれます。 これらの要因により浮動小数点のセマンティクスを有効にすることがあります大幅に低減アプリケーションのパフォーマンスの低下につながる、生成されたマシン コードの効率。

既定では、fp 浮動小数点例外のセマンティクスが有効になっている: 厳格モード。 Fp でこれらのセマンティクスを有効にする: precise モードは、追加、 **/fp: 除く**コマンド ライン コンパイラに切り替えます。 浮動小数点例外のセマンティクスも有効になっているし、を使用して、関数ごとに無効になっている、`float_control`プラグマ。

### <a name="floating-point-exceptions-as-c-exceptions"></a>C++ の例外として、浮動小数点例外

同様すべてのハードウェア例外浮動小数点例外が C++ 例外を本質的に発生しないが、代わりに、構造化例外をトリガーします。 浮動小数点の構造化例外は、C++ 例外にマップするには、ユーザーはカスタム SEH 例外の変換を導入できます。 最初に、各浮動小数点の例外に対応する C++ 例外を導入します。

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

次は、浮動小数点の SEH 例外を検出し、対応する C++ 例外をスローする変換関数を紹介します。 この関数を使用すると、現在のプロセス スレッドのトランスレーターを構造化例外ハンドラーを設定、 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)ランタイム ライブラリから関数。

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

このマッピングが初期化されると、浮動小数点例外は C++ 例外処理のように動作します。 例:

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

## <a name="references"></a>関連項目

[浮動小数点演算について把握する必要がありますすべてのコンピューター科学](http://pages.cs.wisc.edu/~david/courses/cs552/S12/handouts/goldberg-floating-point.pdf)David されるとおり、します。

## <a name="see-also"></a>関連項目

[コードの最適化](../optimizing-your-code.md)<br/>

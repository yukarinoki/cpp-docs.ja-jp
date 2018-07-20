---
title: SafeInt クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce7715553e17e49ef3c169145abfb49816f6d6dd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891338"
---
# <a name="safeint-class"></a>SafeInt クラス
整数オーバーフローを防ぐために役立つ整数プリミティブを拡張し、異なる型の整数を比較できます。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>  
class SafeInt;  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|テンプレート|説明|  
|--------------|-----------------|  
|T|整数またはブール値パラメーターの型を`SafeInt`が置き換えられます。|  
|E|エラー処理ポリシーを定義する列挙型。|  
|U|整数または第 2 オペランドのブール値パラメーターの型。|  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in] rhs|スタンドアロンの関数をいくつかの演算子の右側にある値を表す入力パラメーター。|  
|[in] i|スタンドアロンの関数をいくつかの演算子の右側にある値を表す入力パラメーター。|  
|[in] ビット|スタンドアロンの関数をいくつかの演算子の右側にある値を表す入力パラメーター。|  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SafeInt::SafeInt](../windows/safeint-safeint.md)|既定のコンストラクター|  
  
### <a name="assignment-operators"></a>代入演算子  
  
|名前|構文|  
|----------|------------|  
|=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const U& rhs)`|  
|=|`SafeInt<T,E>& operator= (const T& rhs) throw()`|  
|=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)`|  
|=|`SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()`|  
  
### <a name="casting-operators"></a>キャスト演算子  
  
|名前|構文|  
|----------|------------|  
|bool|`operator bool() throw()`|  
|char|`operator char() const`|  
|signed char|`operator signed char() const`|  
|unsigned char|`operator unsigned char() const`|  
|__int16|`operator __int16() const`|  
|unsigned __int16|`operator unsigned __int16() const`|  
|__int32|`operator __int32() const`|  
|unsigned __int32|`operator unsigned __int32() const`|  
|long|`operator long() const`|  
|unsigned long|`operator unsigned long() const`|  
|__int64|`operator __int64() const`|  
|unsigned __int64|`operator unsigned __int64() const`|  
|wchar_t|`operator wchar_t() const`|  
  
### <a name="comparison-operators"></a>比較演算子  
  
|名前|構文|  
|----------|------------|  
|<|`template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()`|  
|<|`bool operator< (SafeInt<T,E> rhs) const throw()`|  
|>=|`template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()`|  
|>=|`Bool operator>= (SafeInt<T,E> rhs) const throw()`|  
|>|`template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()`|  
|>|`Bool operator> (SafeInt<T,E> rhs) const throw()`|  
|<=|`template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()`|  
|<=|`bool operator<= (SafeInt<T,E> rhs) const throw()`|  
|==|`template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()`|  
|==|`bool operator== (bool rhs) const throw()`|  
|==|`bool operator== (SafeInt<T,E> rhs) const throw()`|  
|!=|`template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()`|  
|!=|`bool operator!= (bool b) const throw()`|  
|!=|`bool operator!= (SafeInt<T,E> rhs) const throw()`|  
  
### <a name="arithmetic-operators"></a>算術演算子  
  
|名前|構文|  
|----------|------------|  
|+|`const SafeInt<T,E>& operator+ () const throw()`|  
|-|`SafeInt<T,E> operator- () const`|  
|++|`SafeInt<T,E>& operator++ ()`|  
|--|`SafeInt<T,E>& operator-- ()`|  
|%|`template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const`|  
|%|`SafeInt<T,E> operator% (SafeInt<T,E> rhs) const`|  
|%=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)`|  
|%=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)`|  
|*|`template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const`|  
|*|`SafeInt<T,E> operator* (SafeInt<T,E> rhs) const`|  
|*=|`SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)`|  
|*=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)`|  
|*=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)`|  
|/|`template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const`|  
|/|`SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const`|  
|/=|`SafeInt<T,E>& operator/= (SafeInt<T,E> i)`|  
|/=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)`|  
|/=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)`|  
|+|`SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const`|  
|+|`template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const`|  
|+=|`SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)`|  
|+=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)`|  
|+=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)`|  
|-|`template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const`|  
|-|`SafeInt<T,E> operator- (SafeInt<T,E> rhs) const`|  
|-=|`SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)`|  
|-=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)`|  
|-=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)`|  
  
### <a name="logical-operators"></a>論理演算子  
  
|名前|構文|  
|----------|------------|  
|!|`bool operator !() const throw()`|  
|~|`SafeInt<T,E> operator~ () const throw()`|  
|<<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()`|  
|<<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()`|  
|<<=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()`|  
|<<=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()`|  
|>>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()`|  
|>>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()`|  
|>>=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()`|  
|>>=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()`|  
|&|`SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()`|  
|&|`template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()`|  
|&=|`SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()`|  
|&=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()`|  
|&=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()`|  
|^|`SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()`|  
|^|`template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()`|  
|^=|`SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()`|  
|^=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()`|  
|^=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()`|  
|&#124;|`SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()`|  
|&#124;|`template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()`|  
|&#124;=|`SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()`|  
|&#124;=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()`|  
|&#124;=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()`|  
  
## <a name="remarks"></a>コメント  
 `SafeInt`クラスが算術演算で整数オーバーフローを防止します。 たとえば、2 つの 8 ビット整数を追加する: 200 の値を持つ 1 つともう 1 つが 100 の値。 適切な数学的な操作は、200 + 100 = 300 になります。 ただし、8 ビット整数の制限のため、上位ビットは失われ、コンパイラが 44 を返す (300 2<sup>8</sup>)、結果として。 この数式に依存しているすべての操作の予期しない動作が生成されます。  
  
 `SafeInt`クラスは、算術オーバーフローが発生するかどうか、またはコードが 0 で除算しようとしたかどうかをチェックします。 どちらの場合は、クラスは、プログラム、可能性のある問題を警告するエラー ハンドラーを呼び出します。  
  
 このクラスではいる限り、2 つの異なる型の整数を比較することもできます`SafeInt`オブジェクト。 通常は、比較を実行するときに、同じ型にするのには数値を最初に変換する必要があります。 多くの場合、1 つの数値を別の型をキャストすると、データの損失がないことを確認するためのチェックが必要です。  
  
 このトピックの内容の演算子の表でサポートされる数学と比較演算子を一覧表示、`SafeInt`クラスです。 最も算術演算子を返す、`SafeInt`型のオブジェクト`T`です。  
  
 比較演算、`SafeInt`整数型をどちらの方向で実行できます。 たとえば、両方とも`SafeInt<int>(x) < y`と`y> SafeInt<int>(x)`は有効では、同じ結果が返されます。  
  
 バイナリ演算子の多くを使用して 2 つの異なるをサポートしていません`SafeInt`型です。 この 1 つの例は、`&`演算子。 `SafeInt<T, E> & int` サポートされているが、`SafeInt<T, E> & SafeInt<U, E>`はありません。 後者の例では、コンパイラは、返されるパラメーターの型を判別できません。 この問題を解決では、基本型に 2 番目のパラメーターをキャストします。 同じパラメーターを使用すると、これと`SafeInt<T, E> & (U)SafeInt<U, E>`です。  
  
> [!NOTE]
>  ビットごとの演算、2 つの異なるパラメーターは同じサイズである必要があります。 サイズが異なる場合、コンパイラがスローされます、 [ASSERT](../mfc/reference/diagnostic-services.md#assert)例外。 この操作の結果は、正確性が保証できません。 この問題を解決するが大きい方のパラメーターと同じサイズになるまで、小さい方のパラメーターをキャストします。  
  
 シフト演算子のテンプレートの型に存在するよりも多くのビットをシフト ASSERT 例外がスローされます。 これは、効果はありませんリリース モードでします。 SafeInt パラメーターの 2 つの型を混在させると、戻り値の型が元の型と同じであるために、シフト演算子可能性があります。 演算子の右側にある数では、シフトするビット数だけを示します。  
  
 SafeInt オブジェクトでの論理比較を実行すると、比較は厳密に算術的です。 たとえば、これらの式があるとします。  
  
-   `SafeInt<uint>((uint)~0) > -1`  
  
-   `((uint)~0) > -1`  
  
 最初のステートメントに解決`true`、2 番目のステートメントに解決されますが、`false`です。 0 のビットごとの否定は、0 xffffffff です。 2 番目のステートメントでは、既定の比較演算子は、0 xffffffff を 0 xffffffff を比較し、両者が等しい場合と見なされます。 比較演算子、`SafeInt`クラスは、最初のパラメーターが符号なし 2 番目のパラメーターが負であることを認識します。 そのため、ビット表現は同じですもには、`SafeInt`論理演算子の符号なし整数が-1 より大きいことに気付きます。  
  
 使用するときに、必ず、`SafeInt`クラスと共に、`?:`三項演算子です。 次のコード行を検討してください。  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : -1;  
```  
  
 コンパイラこれに変換します。  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);  
```  
  
 場合`flag`は`false`、コンパイラが-1 の値を割り当てる代わりに例外をスロー`x`です。 そのため、この問題を回避するには、使用する正しいコードは、次の行です。  
  
```  
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;  
```  
  
 `T` および`U`ブール型、文字型または整数型に割り当てることができます。 型を符号付きまたは符号なし整数と 8 ビットから 64 ビットの任意のサイズ。  
  
> [!NOTE]
>  ただし、`SafeInt`クラスを受け入れる任意の種類の整数、符号なしの型とより効率的に実行します。  
  
 `E` エラー処理機構を`SafeInt`を使用します。 SafeInt ライブラリに 2 つのエラー処理機構が提供されます。 既定のポリシーは`SafeIntErrorPolicy_SafeIntException`、どのがスローされます、 [SafeIntException クラス](../windows/safeintexception-class.md)例外エラーが発生します。 他のポリシーが`SafeIntErrorPolicy_InvalidParameter`エラーが発生した場合、プログラムは停止します。  
  
 エラーのポリシーをカスタマイズする 2 つのオプションがあります。 パラメーターを設定する 1 つ目は`E`を作成するとき、`SafeInt`です。 エラー処理のうちの 1 つのポリシーを変更するときにこのオプションを使用して`SafeInt`です。 その他のオプションは、定義する`_SAFEINT_DEFAULT_ERROR_POLICY`をインクルードする前に、カスタマイズされたエラー処理クラス、`SafeInt`ライブラリです。 既定のエラー処理のすべてのインスタンスのポリシーを変更するときにこのオプションを使用して、`SafeInt`コード内のクラスです。  
  
> [!NOTE]
>  SafeInt ライブラリからエラーを処理するカスタマイズされたクラスは、エラー ハンドラーを呼び出したコードに制御を返しません必要があります。 エラー ハンドラーが呼び出された後の結果、`SafeInt`操作は、信頼することはできません。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>関連項目  
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeIntException クラス](../windows/safeintexception-class.md)
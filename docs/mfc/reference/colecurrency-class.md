---
title: COleCurrency クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleCurrency
- AFXDISP/COleCurrency
- AFXDISP/COleCurrency::COleCurrency
- AFXDISP/COleCurrency::Format
- AFXDISP/COleCurrency::GetStatus
- AFXDISP/COleCurrency::ParseCurrency
- AFXDISP/COleCurrency::SetCurrency
- AFXDISP/COleCurrency::SetStatus
- AFXDISP/COleCurrency::m_cur
- AFXDISP/COleCurrency::m_status
dev_langs:
- C++
helpviewer_keywords:
- COleCurrency [MFC], COleCurrency
- COleCurrency [MFC], Format
- COleCurrency [MFC], GetStatus
- COleCurrency [MFC], ParseCurrency
- COleCurrency [MFC], SetCurrency
- COleCurrency [MFC], SetStatus
- COleCurrency [MFC], m_cur
- COleCurrency [MFC], m_status
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0cdc5c25751da895100155571d6a24705479fd0
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039285"
---
# <a name="colecurrency-class"></a>COleCurrency クラス
OLE オートメーションで使用される `CURRENCY` データ型をカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleCurrency  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleCurrency::COleCurrency](#colecurrency)|`COleCurrency` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleCurrency::Format](#format)|書式設定された文字列表現を生成、`COleCurrency`オブジェクト。|  
|[COleCurrency::GetStatus](#getstatus)|状態を取得します (有効) この`COleCurrency`オブジェクト。|  
|[COleCurrency::ParseCurrency](#parsecurrency)|読み取り、**通貨**文字列から値の値を設定および`COleCurrency`です。|  
|[COleCurrency::SetCurrency](#setcurrency)|この値を設定`COleCurrency`オブジェクト。|  
|[COleCurrency::SetStatus](#setstatus)|状態 (有効) を設定`COleCurrency`オブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[演算子 =](#operator_eq)|コピー、`COleCurrency`値。|  
|[演算子 +、-](#operator_plus_minus)|追加、減算、しの符号を変更`COleCurrency`値。|  
|[演算子 + =、=](#operator_plus_minus_eq)|追加し、減算、`COleCurrency`これから値`COleCurrency`オブジェクト。|  
|[operator */](#operator_star)|スケール、`COleCurrency`の値を整数値。|  
|[演算子 * =、/、=](#operator_star_div_eq)|このスケーリング`COleCurrency`の値を整数値。|  
|[演算子 <<](#operator_stream)|出力、`COleCurrency`値`CArchive`または`CDumpContext`です。|  
|[演算子 >>](#operator_stream)|入力、`COleCurrency`オブジェクトから`CArchive`です。|  
|[演算子の通貨](#operator_currency)|変換、`COleCurrency`値に、**通貨**です。|  
|[演算子 = =、<、< = などです。](#colecurrency_relational_operators)|比較する 2 つ`COleCurrency`値。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleCurrency::m_cur](#m_cur)|含む、基になる**通貨**この`COleCurrency`オブジェクト。|  
|[COleCurrency::m_status](#m_status)|この状態を含む`COleCurrency`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 `COleCurrency` 基本クラスはありません。  
  
 **通貨**8 バイト、2 の補数の整数値が 10,000 を掛けとして実装されます。 これは、15 桁の整数部と 4 桁の小数部を持つ固定小数点数として表現されます。 **通貨**精度が重要なデータ型は関連する計算、またはいずれかの固定小数点計算に非常に便利です。 使用できる型のいずれかである、 `VARIANT` OLE オートメーションのデータ型。  
  
 `COleCurrency` またこの固定小数点型のいくつか基本的な算術演算を実装します。 固定小数点の計算中に発生する丸め誤差を制御するには、サポートされている操作を選択されています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `COleCurrency`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="colecurrency"></a>  COleCurrency::COleCurrency  
 `COleCurrency` オブジェクトを構築します。  
  
```  
COleCurrency();  
COleCurrency(CURRENCY cySrc);  
  COleCurrency(const COleCurrency& curSrc);  
COleCurrency(const VARIANT& varSrc);

 
COleCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>パラメーター  
 *cySrc*  
 A**通貨**新しいにコピーされる値`COleCurrency`オブジェクト。  
  
 *curSrc*  
 既存の`COleCurrency`新しいにコピーされるオブジェクト`COleCurrency`オブジェクト。  
  
 *varSrc*  
 既存の**バリアント**データ構造体 (可能性があります、`COleVariant`オブジェクト) を通貨値に変換する ( `VT_CY`) とに、新しいコピー`COleCurrency`オブジェクト。  
  
 *nUnits*、 *nFractionalUnits*  
 新しいにコピーされるユニットおよび小数部分 (1/10 で、000's) の値を示す`COleCurrency`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 新規作成すべてこれらのコンス トラクターの`COleCurrency`オブジェクトが、指定した値に初期化します。 これらのコンス トラクターのそれぞれの簡単な説明に従います。 限り、新しいステータス`COleCurrency`項目は、有効な設定です。  
  
- COleCurrency() コンストラクト、 `COleCurrency` 0 (ゼロ) に初期化されるオブジェクト。  
  
- COleCurrency (`cySrc`) を構築、`COleCurrency`オブジェクトから、[通貨](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)値。  
  
- COleCurrency (`curSrc`) を構築、 `COleCurrency` 、既存のオブジェクト`COleCurrency`オブジェクト。 新しいオブジェクトには、ソース オブジェクトと同じ状態があります。  
  
- COleCurrency (`varSrc`) を構築、`COleCurrency`オブジェクト。 変換を試みます、[バリアント](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)構造または`COleVariant`通貨型のオブジェクト ( `VT_CY`) 値です。 この変換が成功すると、新しいに変換された値がコピー`COleCurrency`オブジェクト。 値ではない場合、`COleCurrency`オブジェクトがゼロ (0) と無効な状態に設定します。  
  
- `COleCurrency(`nUnits`, `nFractionalUnits`) Constructs a `COleCurrency' オブジェクトを指定した数値のコンポーネントからです。 小数部分の絶対値が 10,000 を超える場合は、単位、適切な調整が行われました。 部と小数部が符号付き long 値によって指定されたことに注意してください。  
  
 詳細については、次を参照してください。、[通貨](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)と[バリアント](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)Windows SDK 内のエントリ。  
  
### <a name="example"></a>例  
 次の例では、パラメーターの 0 と 2 つのパラメーターのコンス トラクターの影響を示します。  
  
 [!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]  
  
##  <a name="format"></a>  COleCurrency::Format  
 通貨値の書式設定された表現を作成するには、このメンバー関数を呼び出します。  
  
```  
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 *dwFlags*  
 ロケールの設定のフラグを示します。 次のフラグのみが通貨に関連します。  
  
- **LOCALE_NOUSEROVERRIDE**カスタムのユーザー設定ではなく、システムの既定のロケール設定を使用します。  
  
 *lcid*  
 変換を使用するロケール ID を示します。  
  
### <a name="return-value"></a>戻り値  
 A`CString`通貨の書式設定された値を格納します。  
  
### <a name="remarks"></a>Remarks  
 ローカル言語仕様 (ロケール Id) を使用して値をフォーマットします。 返される値では、通貨記号は含まれません。 場合のこのステータス`COleCurrency`戻り値は空の文字列は、オブジェクトが null です。 戻り値の文字列が文字列リソースで指定された場合は、状態が有効でない**IDS_INVALID_CURRENCY**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]  
  
##  <a name="getstatus"></a>  COleCurrency::GetStatus  
 状態 (有効) を取得するには、このメンバー関数を呼び出して、指定された`COleCurrency`オブジェクト。  
  
```  
CurrencyStatus GetStatus() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この状態を返します`COleCurrency`値。  
  
### <a name="remarks"></a>Remarks  
 戻り値は、`CurrencyStatus`内で定義されている型を列挙、`COleCurrency`クラスです。  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- **COleCurrency::valid**ことを示しますこの`COleCurrency`オブジェクトは無効にします。  
  
- **COleCurrency::invalid**ことを示しますこの`COleCurrency`オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleCurrency::null**ことを示しますこの`COleCurrency`オブジェクトが null の場合は、このオブジェクトの値が指定されていないこと。 (これは"null"の「値を持たない、」C++ ではなくデータベース意味で**NULL**)。  
  
 状態、`COleCurrency`オブジェクトでは、次の場合。  
  
-   その値が設定されている場合、**バリアント**または`COleVariant`値を通貨値を変換できませんでした。  
  
-   このオブジェクトが発生したため、オーバーフローまたはアンダー フロー代入演算操作中、たとえば場合`+=`または **\* =** です。  
  
-   場合は、無効な値は、このオブジェクトに割り当てられました。  
  
-   このオブジェクトの状態に無効なを使用して明示的に設定された[SetStatus](#setstatus)です。  
  
 操作の詳細については無効です。 次のメンバー関数を参照してください状態を設定することがあります。  
  
- [COleCurrency](#colecurrency)  
  
- [演算子 =](#operator_eq)  
  
- [演算子 + -](#operator_plus_minus)  
  
- [演算子 + = および =](#operator_plus_minus_eq)  
  
- [operator */](#operator_star)  
  
- [演算子 * = および =/](#operator_star_div_eq)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]  
  
##  <a name="m_cur"></a>  COleCurrency::m_cur  
 基になる[通貨](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)この構造体`COleCurrency`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
  
> [!CAUTION]
>  値を変更、**通貨**の値を変更する構造体がこの関数によって返されるポインターは、アクセス`COleCurrency`オブジェクト。 この状態は変更されません`COleCurrency`オブジェクト。  
  
 詳細については、次を参照してください。、[通貨](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)Windows SDK 内のエントリ。  
  
##  <a name="m_status"></a>  COleCurrency::m_status  
 このデータ メンバーの型は列挙型`CurrencyStatus`、内で定義されている、`COleCurrency`クラスです。  
  
```  
enum CurrencyStatus{  
    valid = 0,  
    invalid = 1,  
    null = 2,  
};  
```  
  
### <a name="remarks"></a>Remarks  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- **COleCurrency::valid**ことを示しますこの`COleCurrency`オブジェクトは無効にします。  
  
- **COleCurrency::invalid**ことを示しますこの`COleCurrency`オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleCurrency::null**ことを示しますこの`COleCurrency`オブジェクトが null の場合は、このオブジェクトの値が指定されていないこと。 (これは"null"の「値を持たない、」C++ ではなくデータベース意味で**NULL**)。  
  
 状態、`COleCurrency`オブジェクトでは、次の場合。  
  
-   その値が設定されている場合、**バリアント**または`COleVariant`値を通貨値を変換できませんでした。  
  
-   このオブジェクトが発生したため、オーバーフローまたはアンダー フロー代入演算操作中、たとえば場合`+=`または **\* =** です。  
  
-   場合は、無効な値は、このオブジェクトに割り当てられました。  
  
-   このオブジェクトの状態に無効なを使用して明示的に設定された[SetStatus](#setstatus)です。  
  
 操作の詳細については無効です。 次のメンバー関数を参照してください状態を設定することがあります。  
  
- [COleCurrency](#colecurrency)  
  
- [演算子 =](#operator_eq)  
  
- [演算子 +、-](#operator_plus_minus)  
  
- [演算子 + =、=](#operator_plus_minus_eq)  
  
- [operator */](#operator_star)  
  
- [演算子 * =、/、=](#operator_star_div_eq)  
  
    > [!CAUTION]
    >  このデータ メンバーは、高度なプログラミングに適しています。 インライン メンバー関数を使用する必要があります[GetStatus](#getstatus)と[SetStatus](#setstatus)です。 参照してください`SetStatus`の他の注意に関するこのデータ メンバーを明示的に設定します。  
  
##  <a name="operator_eq"></a>  COleCurrency::operator =  
 これらのオーバー ロードされた代入演算子は、これを元の通貨値をコピー`COleCurrency`オブジェクト。  
  
```  
const COleCurrency& operator=(CURRENCY cySrc);  
const COleCurrency& operator=(const COleCurrency& curSrc);  
  const COleCurrency& operator=(const VARIANT& varSrc);
```  
  
### <a name="remarks"></a>Remarks  
 各演算子の簡単な説明に従います。  
  
- **演算子 = = (** `cySrc` **)** 、`CURRENCY`値にコピーされます、`COleCurrency`オブジェクトとその状態は、有効な設定ができます。  
  
- **演算子 = = (** `curSrc` **)** 値と、既存のオペランドのステータス`COleCurrency`オブジェクトがこれにコピーされます`COleCurrency`オブジェクト。  
  
- **演算子 = = (** *varSrc* **)** 場合の変換、`VARIANT`値 (または[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクト) の通貨に ( `VT_CY`) は成功すると、変換後の値がコピーにこの`COleCurrency`オブジェクトとその状態は、有効な設定されています。 変換が成功すると、ない場合の値、`COleCurrency`オブジェクトが 0 に設定され、状態が無効にします。  
  
 詳細については、次を参照してください。、[通貨](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)と[バリアント](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)Windows SDK 内のエントリ。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]  
  
##  <a name="operator_plus_minus"></a>  COleCurrency::operator +、-  
 これらの演算子を使用すると、加算し、減算 2`COleCurrency`値をおよび互いとの符号を変更する、`COleCurrency`値。  
  
```  
COleCurrency operator+(const COleCurrency& cur) const;  
COleCurrency operator-(const COleCurrency& cur) const;  
COleCurrency operator-() const;  
```  
  
### <a name="remarks"></a>Remarks  
 結果の状態は null オペランドのいずれかの場合`COleCurrency`値は null です。  
  
 かどうか、算術演算オーバーフローすると、その結果、`COleCurrency`値が無効です。  
  
 場合は、オペランドが無効で、もう一方が null でない結果のステータス`COleCurrency`値が無効です。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]  
  
##  <a name="operator_plus_minus_eq"></a>  COleCurrency::operator + =、=  
 加算および減算することは、`COleCurrency`値からこの`COleCurrency`オブジェクト。  
  
```  
const COleCurrency& operator+=(const COleCurrency& cur);  
const COleCurrency& operator-=(const COleCurrency& cur);
```  
  
### <a name="remarks"></a>Remarks  
 この状態は null は、オペランドのいずれかのかどうかは`COleCurrency`オブジェクトが設定を null にします。  
  
 かどうか、算術演算オーバーフローすると、このステータス`COleCurrency`オブジェクトが設定されている無効にします。  
  
 オペランドのいずれかが有効ではなく、もう一方が null でない場合のこのステータス`COleCurrency`オブジェクトが設定されている無効にします。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]  
  
##  <a name="operator_star"></a>  COleCurrency::operator *、/  
 拡大縮小することは、`COleCurrency`の値を整数値。  
  
```  
COleCurrency operator*(long nOperand) const;  
COleCurrency operator/(long nOperand) const;  
```  
  
### <a name="remarks"></a>Remarks  
 場合、`COleCurrency`のオペランドが null の場合、その結果のステータス`COleCurrency`値は null です。  
  
 場合は演算がオーバーフローまたはアンダー フローして、結果のステータス`COleCurrency`値が無効です。  
  
 場合、`COleCurrency`オペランドが有効で、その結果のステータス`COleCurrency`値が無効です。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]  
  
##  <a name="operator_star_div_eq"></a>  COleCurrency::operator * =、/、=  
 スケール アップするのには、`COleCurrency`の値を整数値。  
  
```  
const COleCurrency& operator*=(long nOperand);  
const COleCurrency& operator/=(long nOperand);
```  
  
### <a name="remarks"></a>Remarks  
 場合、`COleCurrency`のオペランドが null の場合、このステータス`COleCurrency`オブジェクトが設定を null にします。  
  
 かどうか、算術演算オーバーフローすると、このステータス`COleCurrency`オブジェクトが設定されている無効にします。  
  
 場合、`COleCurrency`オペランドが無効、このステータス`COleCurrency`オブジェクトが設定されている無効にします。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]  
  
##  <a name="operator_stream"></a>  COleCurrency::operator &lt; &lt;、 &gt;&gt;  
 診断ダンプとアーカイブへの格納をサポートしています。  
  
```  
friend CDumpContext& operator<<(
    CDumpContext& dc,  
    COleCurrency curSrc);
 
friend CArchive& operator<<(
    CArchive& ar,  
    COleCurrency curSrc);
 
friend CArchive& operator>>(
    CArchive& ar,  
    COleCurrency& curSrc);
```  
  
### <a name="remarks"></a>Remarks  
 抽出 ( **>>**) 演算子は、アーカイブからの読み込みをサポートしています。  
  
##  <a name="operator_currency"></a>  COleCurrency::operator 通貨  
 返します、`CURRENCY`構造体の値がこれからコピー`COleCurrency`オブジェクト。  
  
```  
operator CURRENCY() const; 
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="parsecurrency"></a>  COleCurrency::ParseCurrency  
 文字列を解析して通貨値を読み取るには、このメンバー関数を呼び出します。  
  
```  
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,  
    DWORD dwFlags = 0,  
    LCID lcid = LANG_USER_DEFAULT);
 
throw(CMemoryException*); 
throw(COleException*);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszCurrency*  
 解析するのには null で終わる文字列へのポインター。  
  
 *dwFlags*  
 ロケールの設定、フラグのフラグを示します。  
  
- **LOCALE_NOUSEROVERRIDE**カスタムのユーザー設定ではなく、システムの既定のロケール設定を使用します。  
  
 *lcid*  
 変換を使用するロケール ID を示します。  
  
### <a name="return-value"></a>戻り値  
 文字列が通貨値、それ以外の場合 0 を正常に変換された場合は 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 元の文字列内の数値以外の文字の意味は、ローカルの言語仕様 (ロケール Id) を使用します。  
  
 ロケール ID の値の詳細については、次を参照してください。[複数の言語をサポートする](http://msdn.microsoft.com/en-us/47dc5add-232c-4268-b977-43e12da81ede)です。  
  
 文字列が通貨に正常に変換された場合の値、この値`COleCurrency`オブジェクトが有効な値とする状態に設定します。  
  
 文字列を通貨値を変換できませんでしたか数値オーバーフロー、この状態が発生しました`COleCurrency`オブジェクトが無効です。  
  
 文字列の変換は、メモリ割り当てエラーにより失敗した、この関数をスロー、 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)です。 この関数によってスローされる他のエラー状態、 [COleException](../../mfc/reference/coleexception-class.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]  
  
##  <a name="colecurrency_relational_operators"></a>  COleCurrency 関係演算子  
 2 つの通貨値を比較し、条件が true である場合は 0 以外を返しますそれ以外の場合 0 を返します。  
  
```  
BOOL operator==(const COleCurrency& cur) const;  
BOOL operator!=(const COleCurrency& cur) const;  
BOOL operator<(const COleCurrency& cur) const;  
BOOL operator>(const COleCurrency& cur) const;  
BOOL operator<=(const COleCurrency& cur) const;  
BOOL operator>=(const COleCurrency& cur) const;  
```  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  順序付けの操作の戻り値 ( **<**、 **\< =**、 **>**、 **>=**) は、オペランドのいずれかの状態が null または無効な場合は、定義されています。 等値演算子 ( `==`、 `!=`)、オペランドの状態を検討してください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]  
  
##  <a name="setcurrency"></a>  COleCurrency::SetCurrency  
 ユニットと小数部を設定するには、このメンバー関数を呼び出す`COleCurrency`オブジェクト。  
  
```  
void SetCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>パラメーター  
 *nUnits*、 *nFractionalUnits*  
 これにコピーされるユニットおよび小数部分 (1/10 で、000's) の値を示す`COleCurrency`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 小数部分の絶対値が 10,000 を超える場合は、適切な補正、単位を 3 番目の例を次に示すようにします。  
  
 部と小数部が符号付き long 値によって指定されたことに注意してください。 4 番目の次の例は、パラメーターの符号が異なる場合の動作を示しています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]  
  
##  <a name="setstatus"></a>  COleCurrency::SetStatus  
 この状態 (有効) を設定するには、このメンバー関数を呼び出す`COleCurrency`オブジェクト。  
  
```  
void SetStatus(CurrencyStatus  status  );
```  
  
### <a name="parameters"></a>パラメーター  
 *status*  
 この新しいステータス`COleCurrency`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 *ステータス*パラメーターの値がによって定義された、`CurrencyStatus`列挙内で定義されている型、`COleCurrency`クラスです。  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- **COleCurrency::valid**ことを示しますこの`COleCurrency`オブジェクトは無効にします。  
  
- **COleCurrency::invalid**ことを示しますこの`COleCurrency`オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleCurrency::null**ことを示しますこの`COleCurrency`オブジェクトが null の場合は、このオブジェクトの値が指定されていないこと。 (これは"null"の「値を持たない、」C++ ではなくデータベース意味で**NULL**)。  
  
    > [!CAUTION]
    >  この関数は、高度なプログラミング環境です。 この関数では、このオブジェクトのデータは変更されません。 Null または無効な状態を設定する最もよく使用されます。 なお、代入演算子 ([演算子 =](#operator_eq)) および[SetCurrency](#setcurrency)ソース値に基づいて、オブジェクトの状態を設定するには。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleVariant クラス](../../mfc/reference/colevariant-class.md)

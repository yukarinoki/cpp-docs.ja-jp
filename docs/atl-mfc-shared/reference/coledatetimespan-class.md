---
title: '|Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
dev_langs:
- C++
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1941984093879ba22921d19580618ce8caa04b38
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="coledatetimespan-class"></a>しかしクラス
相対的な時間、時間間隔を表します。  
  
## <a name="syntax"></a>構文  
  
```
class COleDateTimeSpan
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|`COleDateTimeSpan` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDateTimeSpan::Format](#format)|書式設定された文字列表現を生成、`COleDateTimeSpan`オブジェクト。|  
|[COleDateTimeSpan::GetDays](#getdays)|このスパンの日付の部分を返します`COleDateTimeSpan`オブジェクトを表します。|  
|[COleDateTimeSpan::GetHours](#gethours)|このスパンの時間部分を返します`COleDateTimeSpan`オブジェクトを表します。|  
|[COleDateTimeSpan::GetMinutes](#getminutes)|このスパンの分の部分を返します`COleDateTimeSpan`オブジェクトを表します。|  
|[COleDateTimeSpan::GetSeconds](#getseconds)|このスパンの 2 番目の部分を返します`COleDateTimeSpan`オブジェクトを表します。|  
|[COleDateTimeSpan::GetStatus](#getstatus)|状態を取得します (有効) この`COleDateTimeSpan`オブジェクト。|  
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|この日数の数を返します`COleDateTimeSpan`オブジェクトを表します。|  
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|この時間の数を返します`COleDateTimeSpan`オブジェクトを表します。|  
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|この分の数を返します`COleDateTimeSpan`オブジェクトを表します。|  
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|この秒数を返します`COleDateTimeSpan`オブジェクトを表します。|  
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|この値を設定`COleDateTimeSpan`オブジェクト。|  
|[COleDateTimeSpan::SetStatus](#setstatus)|これの状態 (有効) に設定`COleDateTimeSpan`オブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|||  
|-|-|  
|[演算子 +、-](#operator_add_-)|追加、減算、および符号を変更`COleDateTimeSpan`値。|  
|[演算子 + =、=](#operator_add_eq_-_eq)|加算および減算、`COleDateTimeSpan`値からこの`COleDateTimeSpan`値。|  
|[演算子 =](#operator_eq)|コピー、`COleDateTimeSpan`値。|  
|[演算子 = =、<、< =](#coledatetimespan_relational_operators)|2 つの比較`COleDateTimeSpan`値。|  
|[演算子 double](#operator_double)|この変換`COleDateTimeSpan`値を**二重**です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleDateTimeSpan::m_span](#m_span)|含む、基になる**二重**この`COleDateTimeSpan`オブジェクト。|  
|[COleDateTimeSpan::m_status](#m_status)|この状態を含む`COleDateTimeSpan`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `COleDateTimeSpan` 基本クラスはありません。  
  
 A`COleDateTimeSpan`日で時間を保持します。  
  
 `COleDateTimeSpan` そのコンパニオン クラスで使用される[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)です。 `COleDateTime` カプセル化、**日付**OLE オートメーションのデータ型。 `COleDateTime` 絶対時刻の値を表します。 すべて`COleDateTime`計算が関係`COleDateTimeSpan`値。 これらのクラス間の関係、間に似ています[CTime](../../atl-mfc-shared/reference/ctime-class.md)と[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)です。  
  
 詳細については、`COleDateTime`と`COleDateTimeSpan`クラスは、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ATLComTime.h  
  
##  <a name="coledatetimespan_relational_operators"></a>  メンバーの関係演算子  
 比較演算子です。  
  
```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *dateSpan*  
 比較対象の `COleDateTimeSpan`。  
  
### <a name="return-value"></a>戻り値  
 これらの演算子は 2 つの日付、期間値を比較し、 **true**条件の場合は true。 それ以外の場合**false**です。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  ATLASSERT がいずれかのオペランドが有効でない場合に発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]  
  
##  <a name="coledatetimespan"></a>  COleDateTimeSpan::COleDateTimeSpan  
 `COleDateTimeSpan` オブジェクトを構築します。  
  
```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dblSpanSrc`  
 新しいにコピーされる日数`COleDateTimeSpan`オブジェクト。  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 新しいにコピーされる日付と時刻の値を示します。`COleDateTimeSpan`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 新規作成すべてこれらのコンス トラクターの`COleDateTimeSpan`オブジェクトが、指定した値に初期化します。 これらのコンス トラクターのそれぞれの簡単な説明に従います。  
  
- **メンバーに関するページ ()** 構築、`COleDateTimeSpan`を 0 に初期化されるオブジェクト。  
  
- **メンバー (** `dblSpanSrc` **)** 構築、`COleDateTimeSpan`浮動小数点値からのオブジェクト。  
  
- **メンバー (** `lDays` **、** `nHours` **、** `nMins` **、** `nSecs` **)** 構築、`COleDateTimeSpan`指定された数値の値に初期化されるオブジェクト。  
  
 新しいステータス`COleDateTimeSpan`オブジェクトが有効に設定されています。  
  
 境界の詳細については`COleDateTimeSpan`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]  
  
##  <a name="format"></a>  COleDateTimeSpan::Format  
 書式設定された文字列表現を生成、`COleDateTimeSpan`オブジェクト。  
  
```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pFormat`  
 書式文字列のような`printf`文字列の書式設定します。 割合に続くコードの書式設定 ( `%`) 署名は、対応する置き換え`COleDateTimeSpan`コンポーネントです。 その他の文字書式指定文字列では、返される文字列に変更されずにコピーされます。 値との書式指定コードの意味**形式**以下に示します。  
  
- **%H**現在の日付の時間  
  
- **%M**で現在の時間 (分)  
  
- **%S**現在の時間 (秒)  
  
- **%%** パーセント記号  
  
 上に示した 4 つの形式のコードは、形式が許容する唯一のコードです。  
  
-  
  
 `nID`  
 コントロールの書式設定文字列のリソース ID。  
  
### <a name="return-value"></a>戻り値  
 A`CString`書式設定された日付、期間値を格納しています。  
  
### <a name="remarks"></a>コメント  
 時間間隔の値の書式設定された表現を作成するこれらの関数を呼び出します。 場合のこのステータス`COleDateTimeSpan`戻り値は空の文字列は、オブジェクトが null です。 戻り値の文字列が文字列リソースで指定された場合は、状態が有効でない**設定されている**です。  
  
 この関数の形式の簡単な説明に従います。  
  
 **書式設定 (** `pFormat` **)**  
 この形式でパーセント記号 (%)、末尾に挿入される特殊な書式設定コードを含む書式指定文字列を使用して値を書式化`printf`です。 書式指定文字列は、関数にパラメーターとして渡されます。  
  
 **書式設定 (** `nID` **)**  
 この形式でパーセント記号 (%)、末尾に挿入される特殊な書式設定コードを含む書式指定文字列を使用して値を書式化`printf`です。 書式指定文字列は、リソースです。 この文字列リソースの ID は、パラメーターとして渡されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]  
  
##  <a name="getdays"></a>  COleDateTimeSpan::GetDays  
 この日付、期間値の日の部分を取得します。  
  
```
LONG GetDays() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値の日の部分です。  
  
### <a name="remarks"></a>コメント  
 戻り値は、約 - この関数の範囲から 3,615,000 と 3,615,000 です。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]  
  
##  <a name="gethours"></a>  COleDateTimeSpan::GetHours  
 この日付、期間値の時間部分を取得します。  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値の時間部分。  
  
### <a name="remarks"></a>コメント  
 この関数の範囲 - 23 ~ 23 からの戻り値。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]  
  
##  <a name="getminutes"></a>  COleDateTimeSpan::GetMinutes  
 この日付、期間値の分の部分を取得します。  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値の分の部分です。  
  
### <a name="remarks"></a>コメント  
 -59 ~ 59 の間には、この関数範囲からの戻り値。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]  
  
##  <a name="getseconds"></a>  COleDateTimeSpan::GetSeconds  
 この日付、期間値の 2 番目の部分を取得します。  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値の秒部分です。  
  
### <a name="remarks"></a>コメント  
 -59 ~ 59 の間には、この関数範囲からの戻り値。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]  
  
##  <a name="getstatus"></a>  COleDateTimeSpan::GetStatus  
 状態を取得します (有効) この`COleDateTimeSpan`オブジェクト。  
  
```
DateTimeSpanStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 このステータス`COleDateTimeSpan`値。  
  
### <a name="remarks"></a>コメント  
 戻り値は、 **DateTimeSpanStatus**列挙内で定義されている型、`COleDateTimeSpan`クラスです。  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
};  
```  
  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- **COleDateTimeSpan::valid**ことを示しますこの`COleDateTimeSpan`オブジェクトは無効にします。  
  
- **COleDateTimeSpan::invalid**ことを示しますこの`COleDateTimeSpan`オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleDateTimeSpan::null**ことを示しますこの`COleDateTimeSpan`オブジェクトが null の場合は、このオブジェクトの値が指定されていないこと。 (これは"null"の「値を持たない、」C++ ではなくデータベース意味で**NULL**)。  
  
 状態、`COleDateTimeSpan`オブジェクトでは、次の場合。  
  
-   このオブジェクトが発生したため、オーバーフローまたはアンダー フロー代入演算操作中、つまり場合、`+=`または`-=`です。  
  
-   場合は、無効な値は、このオブジェクトに割り当てられました。  
  
-   このオブジェクトの状態に無効なを使用して明示的に設定された`SetStatus`です。  
  
 無効な状態を設定することがありますのある操作の詳細については、次を参照してください。 [COleDateTimeSpan::operator +、-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-)と[COleDateTimeSpan::operator + =、-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)です。  
  
 境界の詳細については`COleDateTimeSpan`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
##  <a name="gettotaldays"></a>  COleDateTimeSpan::GetTotalDays  
 日数で表されるこの日付、期間値を取得します。  
  
```
double GetTotalDays() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間は、日数で表される値。 この関数は、double 型の値を返すようにプロトタイプ宣言は、常に整数値を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の範囲の 3.65e6 ~ 3.65e6 からの戻り値。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]  
  
##  <a name="gettotalhours"></a>  COleDateTimeSpan::GetTotalHours  
 時間単位で表すこの日付、期間値を取得します。  
  
```
double GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間は、時間単位で表す値です。 この関数は、double 型の値を返すようにプロトタイプ宣言は、常に整数値を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の範囲の 8.77e7 ~ 8.77e7 からの戻り値。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 例を参照して[誤差](#gettotaldays)です。  
  
##  <a name="gettotalminutes"></a>  COleDateTimeSpan::GetTotalMinutes  
 分数で表されるこの日付、期間値を取得します。  
  
```
double GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値で表される分数を返します。 この関数は、double 型の値を返すようにプロトタイプ宣言は、常に整数値を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の範囲の 5.26e9 ~ 5.26e9 からの戻り値。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 例を参照して[誤差](#gettotaldays)です。  
  
##  <a name="gettotalseconds"></a>  COleDateTimeSpan::GetTotalSeconds  
 この日付、期間値 (秒) を取得します。  
  
```
double GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この日付、期間値 (秒) を返します。 この関数は、double 型の値を返すようにプロトタイプ宣言は、常に整数値を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の戻り値の範囲の間で約 - 3.16e11 に 3.16e11 です。  
  
 その他の関数の値をクエリで、`COleDateTimeSpan`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
### <a name="example"></a>例  
 例を参照して[誤差](#gettotaldays)です。  
  
##  <a name="m_span"></a>  COleDateTimeSpan::m_span  
 基になる**二重**値`COleDateTime`オブジェクト。  
  
```
double m_span;
```  
  
### <a name="remarks"></a>コメント  
 この値は、日の日付/期間を表します。  
  
> [!CAUTION]
>  値を変更、**二重**データ メンバーがこの値を変更`COleDateTimeSpan`オブジェクト。 この状態は変更されません`COleDateTimeSpan`オブジェクト。  
  
##  <a name="m_status"></a>  COleDateTimeSpan::m_status  
 このデータ メンバーの型は列挙型**DateTimeSpanStatus**、内で定義されている、`COleDateTimeSpan`クラスです。  
  
```
DateTimeSpanStatus m_status;
```  
  
### <a name="remarks"></a>コメント  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```  
  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- **COleDateTimeSpan::valid**ことを示しますこの`COleDateTimeSpan`オブジェクトは無効にします。  
  
- **COleDateTimeSpan::invalid**ことを示しますこの`COleDateTimeSpan`オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleDateTimeSpan::null**ことを示しますこの`COleDateTimeSpan`オブジェクトが null の場合は、このオブジェクトの値が指定されていないこと。 (これは"null"の「値を持たない、」C++ ではなくデータベース意味で**NULL**)。  
  
 状態、`COleDateTimeSpan`オブジェクトでは、次の場合。  
  
-   このオブジェクトが発生したため、オーバーフローまたはアンダー フロー代入演算操作中、つまり場合、`+=`または`-=`です。  
  
-   場合は、無効な値は、このオブジェクトに割り当てられました。  
  
-   このオブジェクトの状態に無効なを使用して明示的に設定された[SetStatus](#setstatus)です。  
  
 無効な状態を設定することがありますのある操作の詳細については、次を参照してください。 [COleDateTimeSpan::operator +、-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-)と[COleDateTimeSpan::operator + =、-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)です。  
  
> [!CAUTION]
>  このデータ メンバーは、高度なプログラミングに適しています。 インライン メンバー関数を使用する必要があります[GetStatus](#getstatus)と[SetStatus](#setstatus)です。 参照してください`SetStatus`の他の注意に関するこのデータ メンバーを明示的に設定します。  
  
 境界の詳細については`COleDateTimeSpan`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
##  <a name="operator_eq"></a>  COleDateTimeSpan::operator =  
 コピー、`COleDateTimeSpan`値。  
  
```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```  
  
### <a name="remarks"></a>コメント  
 このオーバー ロードされた代入演算子は、これにソースの日付、期間値をコピー`COleDateTimeSpan`オブジェクト。  
  
##  <a name="operator_add_-"></a>  COleDateTimeSpan::operator +、-  
 追加、減算、および符号を変更`COleDateTimeSpan`値。  
  
```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```  
  
### <a name="remarks"></a>コメント  
 最初の 2 つの演算子では、追加し、日付、期間の値を減算できます。 3 つ目では、日付、期間の値の符号を変更できます。  
  
 結果の状態は null オペランドのいずれかの場合`COleDateTimeSpan`値は null です。  
  
 オペランドのいずれかが有効ではなく、もう一方が null でない場合、その結果のステータス`COleDateTimeSpan`値が無効です。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  COleDateTimeSpan::operator + =、=  
 加算および減算、`COleDateTimeSpan`値からこの`COleDateTimeSpan`値。  
  
```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>コメント  
 これらの演算子では、追加し、これから日付/時間間隔の値を減算できます。`COleDateTimeSpan`オブジェクト。 結果の状態は null オペランドのいずれかの場合`COleDateTimeSpan`値は null です。  
  
 オペランドのいずれかが有効ではなく、もう一方が null でない場合、その結果のステータス`COleDateTimeSpan`値が無効です。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]  
  
##  <a name="operator_double"></a>  二重 COleDateTimeSpan::operator  
 この変換`COleDateTimeSpan`値を**二重**です。  
  
```
operator double() const throw();
```  
  
### <a name="remarks"></a>コメント  
 この演算子は、この値を返します`COleDateTimeSpan`日数の浮動小数点数としての値。  
  
##  <a name="setdatetimespan"></a>  COleDateTimeSpan::SetDateTimeSpan  
 この日付、期間値の値を設定します。  
  
```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 これにコピーされる日付範囲と時間間隔の値を示します。`COleDateTimeSpan`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 関数の値をクエリで、`COleDateTimeSpan`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [誤差](#gettotaldays)  
  
- [従来](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]  
  
##  <a name="setstatus"></a>  COleDateTimeSpan::SetStatus  
 これの状態 (有効) に設定`COleDateTimeSpan`オブジェクト。  
  
```
void SetStatus(DateTimeSpanStatus status) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *status*  
 この新しいステータス値`COleDateTimeSpan`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 *ステータス*パラメーターの値がによって定義された、 **DateTimeSpanStatus**列挙内で定義されている型、`COleDateTimeSpan`クラスです。  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```  
  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- **COleDateTimeSpan::valid**ことを示しますこの`COleDateTimeSpan`オブジェクトは無効にします。  
  
- **COleDateTimeSpan::invalid**ことを示しますこの`COleDateTimeSpan`オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleDateTimeSpan::null**ことを示しますこの`COleDateTimeSpan`オブジェクトが null の場合は、このオブジェクトの値が指定されていないこと。 (これは"null"の「値を持たない、」C++ ではなくデータベース意味で**NULL**)。  
  
    > [!CAUTION]
    >  この関数は、高度なプログラミング環境です。 この関数では、このオブジェクトのデータは変更されません。 状態を設定に使用されるほとんどの場合、`null`または**無効な**します。 なお、代入演算子 ([演算子 =](#eq)) および[SetDateTimeSpan](#setdatetimespan)ソース値に基づいて、オブジェクトの状態を設定しないでください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [COleDateTime クラス](../../atl-mfc-shared/reference/coledatetime-class.md)   
 [CTime クラス](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan クラス](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)



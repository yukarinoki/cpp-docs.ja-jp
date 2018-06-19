---
title: CTimeSpan クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
dev_langs:
- C++
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd95d26dd2df41f16091379c892f67319c218cc4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365319"
---
# <a name="ctimespan-class"></a>CTimeSpan クラス
時間間隔の秒数として内部的に格納されている時間の量。  
  
## <a name="syntax"></a>構文  
  
```
class CTimeSpan
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CTimeSpan::CTimeSpan](#ctimespan)|構築`CTimeSpan`さまざまな方法でオブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTimeSpan::Format](#format)|変換、`CTimeSpan`を書式設定された文字列にします。|  
|[CTimeSpan::GetDays](#getdays)|これで完了日の数を表す値を返します`CTimeSpan`です。|  
|[CTimeSpan::GetHours](#gethours)|現在の日付 (-23 ~ 23) の時間数を表す値を返します。|  
|[CTimeSpan::GetMinutes](#getminutes)|現在の時間 (-59 ~ 59) で分単位の数を表す値を返します。|  
|[CTimeSpan::GetSeconds](#getseconds)|現在の分 (-59 ~ 59) の秒数を表す値を返します。|  
|[CTimeSpan::GetTimeSpan](#gettimespan)|値を返します、`CTimeSpan`オブジェクト。|  
|[CTimeSpan::GetTotalHours](#gettotalhours)|これで完了時間の合計数を表す値を返します`CTimeSpan`です。|  
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|この分数の合計数を表す値を返します`CTimeSpan`です。|  
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|これで完了秒の合計数を表す値を返します`CTimeSpan`です。|  
|[CTimeSpan::Serialize64](#serialize64)|またはアーカイブからデータをシリアル化します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 + -](#operator_add_-)|追加し、減算`CTimeSpan`オブジェクト。|  
|[演算子 + = =](#operator_add_eq_-_eq)|追加し、減算、`CTimeSpan`オブジェクトからこの`CTimeSpan`です。|  
|[演算子 = = < などです。](#ctimespan_comparison_operators)|2 つの相対時間値を比較します。|  
  
## <a name="remarks"></a>コメント  
 `CTimeSpan` 基本クラスはありません。  
  
 `CTimeSpan` 関数は、さまざまな組み合わせで、日、時間、分、秒および秒に変換します。  
  
 `CTimeSpan`にオブジェクトが格納されている、 **_ _time64_t**構造体は、8 バイトです。  
  
 コンパニオン クラス[CTime](../../atl-mfc-shared/reference/ctime-class.md)、絶対時刻を表します。  
  
 `CTime`と`CTimeSpan`クラスが派生させるために設計されていません。 両方のサイズの仮想関数が存在しないため`CTime`と`CTimeSpan`オブジェクトは、厳密に 8 バイト。 ほとんどのメンバー関数はインラインです。  
  
 使用する方法について`CTimeSpan`、記事を参照して[日付と時刻](../../atl-mfc-shared/date-and-time.md)、および[時間管理](../../c-runtime-library/time-management.md)で、*ランタイム ライブラリ リファレンス*です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltime.h  
  
##  <a name="ctimespan_comparison_operators"></a>  CTimeSpan 比較演算子  
 比較演算子です。  
  
```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
  
 比較対象のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 これらの演算子は、2 つの相対時間値を比較します。 返される**true**条件の場合は true。 それ以外の場合**false**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]  
  
##  <a name="ctimespan"></a>  CTimeSpan::CTimeSpan  
 構築`CTimeSpan`さまざまな方法でオブジェクト。  
  
```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(  
 LONG lDays,
 int nHours,
 int nMins,
 int nSecs) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *timeSpanSrc*  
 A`CTimeSpan`既に存在するオブジェクト。  
  
 `time`  
 A **_ _time64_t**時間間隔の秒数は、時刻の値。  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 日、時間、分、および秒、それぞれします。  
  
### <a name="remarks"></a>コメント  
 これらすべてのコンストラクタは、新しい作成`CTimeSpan`指定の相対時刻で初期化されるオブジェクト。 各コンス トラクターは、次に示します。  
  
- **CTimeSpan ();** 構築、初期化されていない`CTimeSpan`オブジェクト。  
  
- **CTimeSpan (const CTimeSpan (& a)) です。** 構築、`CTimeSpan`から別のオブジェクト`CTimeSpan`値。  
  
- **CTimeSpan (_ _time64_t) です。** 構築、`CTimeSpan`オブジェクトから、 **_ _time64_t**型です。  
  
- **CTimeSpan (長い**、 **int, int, int);** 構築、`CTimeSpan`オブジェクトの各構成要素からは、次の範囲に制限します。  
  
    |コンポーネント|範囲|  
    |---------------|-----------|  
    |`lDays`|0-25,000 (概算)|  
    |`nHours`|0-23|  
    |`nMins`|0-59|  
    |`nSecs`|0-59|  
  
 Microsoft Foundation Class ライブラリのデバッグ バージョンでは、1 つ以上の時間帯は、コンポーネントが範囲外アサートすることに注意してください。 ユーザーの責任を呼び出す前に引数を検証することをお勧めします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]  
  
##  <a name="format"></a>  CTimeSpan::Format  
 これに対応する書式設定された文字列を生成`CTimeSpan`です。  
  
```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pFormat`, `pszFormat`  
 書式文字列のような`printf`文字列の書式設定します。 割合に続くコードの書式設定 ( `%`) 署名は、対応する置き換え`CTimeSpan`コンポーネントです。 その他の文字書式指定文字列では、返される文字列に変更されずにコピーされます。 値との書式指定コードの意味**形式**以下に示します。  
  
- **%D**この日数の合計 `CTimeSpan`  
  
- **%H**現在の日付の時間  
  
- **%M**で現在の時間 (分)  
  
- **%S**現在の時間 (秒)  
  
- **%%** パーセント記号  
  
 `nID`  
 この形式を識別する文字列の ID。  
  
### <a name="return-value"></a>戻り値  
 A`CString`書式設定された時間を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ライブラリのデバッグ バージョンでは、書式指定コードをチェックし、コードは、上記の一覧に含まれないかどうかをアサートします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]  
  
##  <a name="getdays"></a>  CTimeSpan::GetDays  
 これで完了日の数を表す値を返します`CTimeSpan`です。  
  
```
LONGLONG GetDays() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 時間間隔内には 24 日単位の数を返します。 この値は、時間間隔が負の場合は、負である可能性があります。  
  
### <a name="remarks"></a>コメント  
 夏時間の原因となる注`GetDays`可能性があることにより意外結果が返されます。 たとえば、ときに夏時間が有効で**GetDays**年 4 月 1 日 1 時間を短縮し、そのため、1 日に完了とは見なされませんのでない 30 日、29 と 4 月 1 日から 5 月 1日までの日数の数を報告します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]  
  
##  <a name="gethours"></a>  CTimeSpan::GetHours  
 現在の日付 (-23 ~ 23) の時間数を表す値を返します。  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 現在の日付の時間数を返します。 範囲は、-23 ~ 23 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]  
  
##  <a name="getminutes"></a>  CTimeSpan::GetMinutes  
 現在の時間 (-59 ~ 59) で分単位の数を表す値を返します。  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 現在の時刻の分単位の数を返します。 範囲は、-59 ~ 59 です。  
  
### <a name="example"></a>例  
 例を参照して[GetHours](#gethours)です。  
  
##  <a name="getseconds"></a>  CTimeSpan::GetSeconds  
 現在の分 (-59 ~ 59) の秒数を表す値を返します。  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 現在の分の秒数を返します。 範囲は、-59 ~ 59 です。  
  
### <a name="example"></a>例  
 例を参照して[GetHours](#gethours)です。  
  
##  <a name="gettimespan"></a>  CTimeSpan::GetTimeSpan  
 値を返します、`CTimeSpan`オブジェクト。  
  
```
__ time64_t GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 現在の値を返します、`CTimeSpan`オブジェクト。  
  
##  <a name="gettotalhours"></a>  CTimeSpan::GetTotalHours  
 これで完了時間の合計数を表す値を返します`CTimeSpan`です。  
  
```
LONGLONG GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 これで完了時間の合計数を返します`CTimeSpan`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]  
  
##  <a name="gettotalminutes"></a>  CTimeSpan::GetTotalMinutes  
 この分数の合計数を表す値を返します`CTimeSpan`です。  
  
```
LONGLONG GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この分数の合計数を返します`CTimeSpan`です。  
  
### <a name="example"></a>例  
 例を参照して[従来](#gettotalhours)です。  
  
##  <a name="gettotalseconds"></a>  CTimeSpan::GetTotalSeconds  
 これで完了秒の合計数を表す値を返します`CTimeSpan`です。  
  
```
LONGLONG GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 これで完了秒の合計数を返します`CTimeSpan`です。  
  
### <a name="example"></a>例  
 例を参照して[従来](#gettotalhours)です。  
  
##  <a name="operator_add_-"></a>  CTimeSpan::operator +、-  
 追加し、減算`CTimeSpan`オブジェクト。  
  
```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 追加する値、`CTimeSpan`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 A`CTimeSpan`操作の結果を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 これら 2 つの演算子を使用すると、加算し、減算`CTimeSpan`をおよび他のオブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  CTimeSpan::operator + =、=  
 追加し、減算、`CTimeSpan`オブジェクトからこの`CTimeSpan`です。  
  
```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 追加する値、`CTimeSpan`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新された`CTimeSpan`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 これらの演算子を使用すると、加算し、減算、`CTimeSpan`オブジェクトからこの`CTimeSpan`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]  
  
##  <a name="serialize64"></a>  CTimeSpan::Serialize64  
  
> [!NOTE]
>  このメソッドを MFC プロジェクトで使用できるだけです。  
  
 メンバー変数とアーカイブの間に関連付けられているデータをシリアル化します。  
  
```
CArchive& Serialize64(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 `ar`  
 `CArchive`を更新するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新された`CArchive`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime、wcsftime、_strftime_l、_wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)



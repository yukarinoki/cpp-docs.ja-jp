---
title: COleDateTime クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDateTime
- ATLCOMTIME/ATL::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::Format
- ATLCOMTIME/ATL::COleDateTime::GetAsDBTIMESTAMP
- ATLCOMTIME/ATL::COleDateTime::GetAsSystemTime
- ATLCOMTIME/ATL::COleDateTime::GetAsUDATE
- ATLCOMTIME/ATL::COleDateTime::GetCurrentTime
- ATLCOMTIME/ATL::COleDateTime::GetDay
- ATLCOMTIME/ATL::COleDateTime::GetDayOfWeek
- ATLCOMTIME/ATL::COleDateTime::GetDayOfYear
- ATLCOMTIME/ATL::COleDateTime::GetHour
- ATLCOMTIME/ATL::COleDateTime::GetMinute
- ATLCOMTIME/ATL::COleDateTime::GetMonth
- ATLCOMTIME/ATL::COleDateTime::GetSecond
- ATLCOMTIME/ATL::COleDateTime::GetStatus
- ATLCOMTIME/ATL::COleDateTime::GetYear
- ATLCOMTIME/ATL::COleDateTime::ParseDateTime
- ATLCOMTIME/ATL::COleDateTime::SetDate
- ATLCOMTIME/ATL::COleDateTime::SetDateTime
- ATLCOMTIME/ATL::COleDateTime::SetStatus
- ATLCOMTIME/ATL::COleDateTime::SetTime
- ATLCOMTIME/ATL::COleDateTime::m_dt
- ATLCOMTIME/ATL::COleDateTime::m_status
dev_langs:
- C++
helpviewer_keywords:
- shared classes, COleDateTime
- time-only values
- Date data type, MFC encapsulation of
- COleDateTime class
- dates, handling in MFC
- time, handling in MFC
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ac939714eff9473397cbe50075f3082f38cdf23
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366277"
---
# <a name="coledatetime-class"></a>COleDateTime クラス
カプセル化、 `DATE` OLE オートメーションで使用されているデータ型。  
  
## <a name="syntax"></a>構文  
  
```
class COleDateTime
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDateTime::COleDateTime](#coledatetime)|`COleDateTime` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[近く](#format)|書式設定された文字列表現を生成、`COleDateTime`オブジェクト。|  
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|時刻を取得するには、このメソッドを呼び出す、`COleDateTime`オブジェクトとして、 **DBTIMESTAMP**データ構造体。|  
|[COleDateTime::GetAsSystemTime](#getassystemtime)|時刻を取得するには、このメソッドを呼び出す、`COleDateTime`オブジェクトとして、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)データ構造体。|  
|[COleDateTime::GetAsUDATE](#getasudate)|時刻を取得するには、このメソッドを呼び出す、`COleDateTime`として、 **UDATE**データ構造体。|  
|[COleDateTime::GetCurrentTime](#getcurrenttime)|作成、`COleDateTime`を現在の時刻 (静的メンバー関数) を表すオブジェクト。|  
|[COleDateTime::GetDay](#getday)|この日を返します`COleDateTime`オブジェクトを表します (1 ~ 31)。|  
|[COleDateTime::GetDayOfWeek](#getdayofweek)|この週の曜日を返します`COleDateTime`オブジェクトが表す (日曜日 = 1)。|  
|[COleDateTime::GetDayOfYear](#getdayofyear)|これで、年の日付を返します`COleDateTime`オブジェクトが表す (1 月 1 日 = 1)。|  
|[COleDateTime::GetHour](#gethour)|この時間を返します`COleDateTime`オブジェクトが表す (0 ~ 23)。|  
|[COleDateTime::GetMinute](#getminute)|この分を返します`COleDateTime`オブジェクトが表す (0 ~ 59)。|  
|[COleDateTime::GetMonth](#getmonth)|この月を返します`COleDateTime`オブジェクトを表します (1 ~ 12)。|  
|[COleDateTime::GetSecond](#getsecond)|この秒を返します`COleDateTime`オブジェクトが表す (0 ~ 59)。|  
|[「](#getstatus)|状態を取得します (有効) この`COleDateTime`オブジェクト。|  
|[COleDateTime::GetYear](#getyear)|これは年を返します`COleDateTime`オブジェクトを表します。|  
|[COleDateTime::ParseDateTime](#parsedatetime)|文字列から日付/時刻値を読み取るしの値を設定`COleDateTime`です。|  
|[COleDateTime::SetDate](#setdate)|この値を設定`COleDateTime`オブジェクトを指定した日付のみの値にします。|  
|[COleDateTime::SetDateTime](#setdatetime)|この値を設定`COleDateTime`オブジェクトを指定した日付/時刻値にします。|  
|[COleDateTime::SetStatus](#setstatus)|これの状態 (有効) に設定`COleDateTime`オブジェクト。|  
|[COleDateTime::SetTime](#settime)|この値を設定`COleDateTime`オブジェクトを指定の時間専用の値にします。|  
  
### <a name="public-operators"></a>パブリック演算子  

|名前|説明|  
|----------|-----------------|  
|[COleDateTime::operator = =、COleDateTime::operator <, などです。](#coledatetime_relational_operators)|2 つの比較`COleDateTime`値。|  
|[COleDateTime::operator +、- COleDateTime::operator](#operator_add_-)|加算および減算`COleDateTime`値。|  
|[COleDateTime::operator + =、-= COleDateTime::operator](#operator_add_eq_-_eq)|加算および減算、`COleDateTime`これから値`COleDateTime`オブジェクト。|  
|[COleDateTime::operator =](#operator_eq)|コピー、`COleDateTime`値。|  
|[COleDateTime::operator 日付、COleDateTime::operator 日付 *](#operator_date)|変換、`COleDateTime`値に、`DATE`または`DATE*`です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleDateTime::m_dt](#m_dt)|含む、基になる**日付**この`COleDateTime`オブジェクト。|  
|[COleDateTime::m_status](#m_status)|この状態を含む`COleDateTime`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `COleDateTime` 基本クラスはありません。  
  
 使用できる型のいずれかである、[バリアント](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)OLE オートメーションのデータ型。 A`COleDateTime`値は、絶対日付と時刻の値を表します。  
  
 `DATE`浮動小数点値の型を実装します。 日数は 1899 年 12 月 30 日の午前 0 時に測定されます。 次の表は、一部の日付とその関連値を示しています。  
  
|日付|[値]|  
|----------|-----------|  
|1899 年 12 月 29 日午前 0 時|-1.0|  
|1899 年 12 月 29 日午前 6 時|-1.25|  
|1899 年 12 月 30 日の午前 0 時|0.0|  
|1899 年 12 月 31 日の午前 0 時|1|  
|1900 年 1 月 1 日午前 6 時|2.25|  
  
> [!CAUTION]
>  上記の表に、1899 年 12 月 30 日の午前 0 時前に 1 日の値が負の値になりますが時刻の値は注意してください。 たとえば、6時 00分 AM は常に日付を表す整数は、(変更後、1899 年 12 月 30 日) 正または負 (1899 年 12 月 30 日) の前にするかどうかに関係なく、小数部の値 0.25 で表されます。 つまり、浮動小数点ポイントの単純な比較が誤って並べ替えることが、 `COleDateTime` 12/29/1899 として 6時 00分 AM を表す**後**1 よりも、同じ日に 7時 00分 AM を表すです。  
  
 `COleDateTime`クラスは 9999 100 年 1 月 1 日 12 月 31 日までの日付を処理します。 `COleDateTime`クラスは構成のグレゴリオ暦カレンダーを使用して; ユリウス暦をサポートしていません。 `COleDateTime` 夏時間を無視します。 (を参照してください[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md))。  
  
> [!NOTE]
>  使用することができます、`%y`形式の日付は 1900 年以降だけ 2 桁の年を取得します。 使用する場合、 `%y` 1900 年より前に、の日付、コードで形式がアサート エラーを生成します。  
  
 この型は、日付だけ、または時間専用の値を表すも使用されます。 慣例により、時刻のみの値を 0 (1899 年 12 月 30 日) の日付が使用され、日付のみの値の時刻 00:00 (午前 0 時) を使用します。  
  
 作成する場合、`COleDateTime`日付を使用して、オブジェクト数が 100 未満、日付が、許容されるが、後続の呼び出しを`GetYear`、 `GetMonth`、 `GetDay`、 `GetHour`、`GetMinute`と`GetSecond`失敗し、-1 を返します。 以前は、2 桁の数字の日付を使用する可能性がありますが、日付が 100 または MFC 4.2 でより大きなおよびそれ以降にする必要があります。  
  
 問題を回避するのには、4 桁の日付を指定します。 例えば:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]  
  
 基本的な算術演算、`COleDateTime`値コンパニオン クラスを使用して[メンバー](../../atl-mfc-shared/reference/coledatetimespan-class.md)です。 `COleDateTimeSpan` 値は、時間間隔を定義します。 これらのクラス間のリレーションシップと似ていますが、間[CTime](../../atl-mfc-shared/reference/ctime-class.md)と[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)です。  
  
 詳細については、`COleDateTime`と`COleDateTimeSpan`クラスは、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ATLComTime.h  
  
##  <a name="coledatetime_relational_operators"></a>  COleDateTime 関係演算子  
 比較演算子です。  
  
```
bool operator==(const COleDateTime& date) const throw();
bool operator!=(const COleDateTime& date) const throw();
bool operator<(const COleDateTime& date) const throw();
bool operator>(const COleDateTime& date) const throw();
bool operator<=(const COleDateTime& date) const throw();
bool operator>=(const COleDateTime& date) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `date`  
 **COleDateTime**と比較するオブジェクト。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  ATLASSERT が 2 つのオペランドのいずれかが有効ではない場合に発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]  
  
### <a name="example"></a>例  
 演算子は、 **>=**、 **\< =**、 **>**、および**<**、場合にアサートされます、`COleDateTime`オブジェクトが設定を null にします。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]  
  
##  <a name="coledatetime"></a>  COleDateTime::COleDateTime  
 `COleDateTime` オブジェクトを構築します。  
  
```
COleDateTime() throw();
COleDateTime(const VARIANT& varSrc) throw();
COleDateTime(DATE dtSrc) throw();
COleDateTime(time_t timeSrc) throw();
COleDateTime(__time64_t timeSrc) throw();
COleDateTime(const SYSTEMTIME& systimeSrc) throw();
COleDateTime(const FILETIME& filetimeSrc) throw();

COleDateTime(int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();

COleDateTime(WORD wDosDate,
    WORD wDosTime) throw();
COleDateTime(const DBTIMESTAMP& dbts) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dateSrc`  
 既存の`COleDateTime`新しいにコピーされるオブジェクト`COleDateTime`オブジェクト。  
  
 *varSrc*  
 既存の**バリアント**データ構造体 (可能性のある、`COleVariant`オブジェクト) 日付/時刻値に変換する ( `VT_DATE`) とに、新しいコピー`COleDateTime`オブジェクト。  
  
 `dtSrc`  
 日付/時刻 (**日付**) にコピーされる新しい値`COleDateTime`オブジェクト。  
  
 `timeSrc`  
 A`time_t`または **_ _time64_t**日付/時刻値に変換され、新しいにコピーされる値`COleDateTime`オブジェクト。  
  
 *systimeSrc*  
 A`SYSTEMTIME`日付/時刻値に変換され、新しいコピーを構造`COleDateTime`オブジェクト。  
  
 `filetimeSrc`  
 A`FILETIME`日付/時刻値に変換され、新しいコピーを構造`COleDateTime`オブジェクト。 なお`FILETIME`世界協定時刻 (UTC) を使用してため、構造のローカル時刻を渡した場合、結果は不正確になります。 参照してください[ファイル時間](http://msdn.microsoft.com/library/windows/desktop/ms724290)詳細については、Windows SDK に含まれています。  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 新しいにコピーされる日付と時刻の値を示します。`COleDateTime`オブジェクト。  
  
 `wDosDate`, `wDosTime`  
 MS-DOS 日付と時刻の値は、日付/時刻値に変換され、新しいコピー`COleDateTime`オブジェクト。  
  
 `dbts`  
 参照、 [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype)現在の現地時刻を含む構造体。  
  
### <a name="remarks"></a>コメント  
 これらすべてのコンストラクタが新規作成`COleDateTime`オブジェクトが、指定した値に初期化します。 次の表は、各日付と時刻のコンポーネントの有効な範囲を示しています。  
  
|日付/時刻コンポーネント|有効範囲|  
|--------------------------|-----------------|  
|年|100 - 9999|  
|月|0 - 12|  
|日|0 - 31|  
|1 時間|0 - 23|  
|1 分|0 - 59|  
|1 秒|0 - 59|  
  
 日付部分の実際の上限の境界が変化するメモは、月と年のコンポーネントに基づいています。 詳細については、次を参照してください。、 **SetDate**または`SetDateTime`メンバー関数。  
  
 各コンス トラクターの簡単な説明を次に示します。  
  
- `COleDateTime(` **)** 構築、 `COleDateTime` 0 (午前 0 時、1899 年 12 月 30日) に初期化されるオブジェクト。  
  
- `COleDateTime(` `dateSrc` **)** 構築、 `COleDateTime` 、既存のオブジェクト`COleDateTime`オブジェクト。  
  
- `COleDateTime(` *varSrc* **)** 構築、`COleDateTime`オブジェクト。 変換を試みます、`VARIANT`構造または[COleVariant](../../mfc/reference/colevariant-class.md)を日付/時刻オブジェクト ( `VT_DATE`) 値です。 この変換が成功すると、新しいに変換された値がコピー`COleDateTime`オブジェクト。 値ではない場合、`COleDateTime`オブジェクトの値が 0 (午前 0 時、1899 年 12 月 30日)、その状態は無効にします。  
  
- `COleDateTime(` `dtSrc` **)** 構築、`COleDateTime`オブジェクトから、**日付**値。  
  
- `COleDateTime(` `timeSrc` **)** 構築、`COleDateTime`オブジェクトから、`time_t`値。  
  
- `COleDateTime(` *systimeSrc* **)** 構築、`COleDateTime`オブジェクトから、`SYSTEMTIME`値。  
  
- `COleDateTime(` `filetimeSrc` **)** 構築、`COleDateTime`オブジェクトから、`FILETIME`値。 である必要があります。 なお`FILETIME`世界協定時刻 (UTC) を使用してため、構造のローカル時刻を渡した場合、結果は不正確になります。 参照してください[ファイル時間](http://msdn.microsoft.com/library/windows/desktop/ms724290)詳細については、Windows SDK に含まれています。  
  
- `COleDateTime(` `nYear`、 `nMonth`、 `nDay`、 `nHour`、 `nMin`、 `nSec` **)** 構築、`COleDateTime`オブジェクトから指定した数値。  
  
- `COleDateTime(` `wDosDate`、 `wDosTime` **)** 構築、 `COleDateTime` MS-DOS 日付と時刻の値は、指定したオブジェクト。  
  
 詳細については、`time_t`データ型を参照してください、[時間](../../c-runtime-library/reference/time-time32-time64.md)で機能、*ランタイム ライブラリ リファレンス*です。  
  
 詳細については、次を参照してください。、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)と[FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Windows SDK 内の構造体。  
  
 境界の詳細については`COleDateTime`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
> [!NOTE]
>  コンス トラクターを使用して、 **DBTIMESTAMP**パラメーターは、OLEDB.h が含まれる場合にのみ使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]  
  
##  <a name="format"></a>  近く  
 日付/時刻値の書式設定された表現を作成します。  
  
```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 次のロケール フラグのいずれかを示します。  
  
- `LOCALE_NOUSEROVERRIDE` システムの既定のロケール設定を使用して、カスタム ユーザー設定の代わりにします。  
  
- `VAR_TIMEVALUEONLY` 解析中に、日付部分を無視します。  
  
- `VAR_DATEVALUEONLY` 解析中に時刻部分を無視します。  
  
 `lcid`  
 変換を使用するロケール ID を示します。 言語識別子の詳細については、次を参照してください。[言語識別子](http://msdn.microsoft.com/library/windows/desktop/dd318691)です。  
  
 `lpszFormat`  
 書式文字列のような`printf`文字列の書式設定します。 各書式指定コード、前に、% ( `%`) 署名と、対応する置き換え`COleDateTime`コンポーネントです。 その他の文字書式指定文字列では、返される文字列に変更されずにコピーされます。 実行時の関数を参照して[strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)詳細についてはします。 値との書式指定コードの意味`Format`は。  
  
- `%H` 現在の日付の時間  
  
- `%M` 現在の時間内 (分)  
  
- `%S` 現在の時間 (秒)  
  
- `%%` パーセント記号  
  
 `nFormatID`  
 コントロールの書式設定文字列のリソース ID。  
  
### <a name="return-value"></a>戻り値  
 A`CString`書式設定された日付/時刻値を格納します。  
  
### <a name="remarks"></a>コメント  
 場合のこのステータス`COleDateTime`戻り値は空の文字列は、オブジェクトが null です。 戻り値の文字列が文字列リソースで指定された場合は、状態が有効でない`ATL_IDS_DATETIME_INVALID`です。  
  
 この関数の 3 つの形式の簡単な説明に従います。  
  
 `Format`( `dwFlags`, `lcid`)  
 このフォームは、日付と時刻の言語仕様 (ロケール Id) を使用して値を形式です。 既定のパラメーターを使用して、このフォームで印刷されます、日付と時刻、またはしない限り、時刻部分は、0 (深夜)、その場合は日付のみが出力されます、日付部分は、0 (30 1899 年 12 月)、その場合、時刻だけが出力されます。 日付/時刻値が 0 (30 1899 年 12 月、午前 0 時) の場合、既定のパラメーターには、このフォームは午前 0 時を印刷します。  
  
 `Format`( `lpszFormat`)  
 この形式でパーセント記号 (%)、末尾に挿入される特殊な書式設定コードを含む書式指定文字列を使用して値を書式化`printf`です。 書式指定文字列は、関数にパラメーターとして渡されます。 書式指定コードの詳細については、次を参照してください。 [strftime、wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)ランタイム ライブラリ リファレンスです。  
  
 `Format`( `nFormatID`)  
 この形式でパーセント記号 (%)、末尾に挿入される特殊な書式設定コードを含む書式指定文字列を使用して値を書式化`printf`です。 書式指定文字列は、リソースです。 この文字列リソースの ID は、パラメーターとして渡されます。 書式指定コードの詳細については、次を参照してください。 [strftime、wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)で、*ランタイム ライブラリ リファレンス*です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]  
  
##  <a name="getasdbtimestamp"></a>  COleDateTime::GetAsDBTIMESTAMP  
 時刻を取得するには、このメソッドを呼び出す、`COleDateTime`オブジェクトとして、 **DBTIMESTAMP**データ構造体。  
  
```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dbts`  
 参照、 [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype)構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 結果として得られる時刻を、参照されている `dbts` 構造体に格納します。 **DBTIMESTAMP**この関数によって初期化されたデータ構造が含まれ、**分数**メンバーが 0 に設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]  
  
##  <a name="getassystemtime"></a>  COleDateTime::GetAsSystemTime  
 時刻を取得するには、このメソッドを呼び出す、`COleDateTime`オブジェクトとして、`SYSTEMTIME`データ構造体。  
  
```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *sysTime*  
 参照、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)から変換された日付/時刻値を受け取る、`COleDateTime`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**成功した場合**false** 、変換に失敗した場合、または場合、`COleDateTime`オブジェクトが**NULL**か、無効です。  
  
### <a name="remarks"></a>コメント  
 `GetAsSystemTime` 参照先の結果として得られる時刻を格納*sysTime*オブジェクト。 `SYSTEMTIME`この関数によって初期化されたデータ構造が含まれ、 **wMilliseconds**メンバーが 0 に設定します。  
  
 参照してください[GetStatus](#getstatus)ステータス情報の詳細についてに保持されているため、`COleDateTime`オブジェクト。  
  
##  <a name="getasudate"></a>  COleDateTime::GetAsUDATE  
 時刻を取得するには、このメソッドを呼び出す、`COleDateTime`オブジェクトとして、 **UDATE**データ構造体。  
  
```
bool GetAsUDATE(UDATE& udate) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `udate`  
 参照、 **UDATE**から変換された日付/時刻値を受け取る、`COleDateTime`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**成功した場合**false** 、変換に失敗した場合、または場合、`COleDateTime`オブジェクトが**NULL**か、無効です。  
  
### <a name="remarks"></a>コメント  
 A **UDATE**構造体は、「展開」の日付を表します。  
  
##  <a name="getcurrenttime"></a>  COleDateTime::GetCurrentTime  
 現在の日付/時刻値を返すには、この静的メンバー関数を呼び出します。  
  
```
static COleDateTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]  
  
##  <a name="getday"></a>  COleDateTime::GetDay  
 この日付/時刻値で表される月の日を取得します。  
  
```
int GetDay() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値で表される月の日にち`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、1 日を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値の 1 ~ 31 の範囲です。  
  
 この値をクエリするその他のメンバー関数の詳細について`COleDateTime`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]  
  
##  <a name="getdayofweek"></a>  COleDateTime::GetDayOfWeek  
 この日付/時刻値で表される月の日を取得します。  
  
```
int GetDayOfWeek() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値で表される曜日`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、週の曜日を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値は 1 ~ 7、範囲、ここで、1 = 日曜日、2 = 月曜日、しにします。  
  
 この値をクエリするその他のメンバー関数の詳細について`COleDateTime`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]  
  
##  <a name="getdayofyear"></a>  COleDateTime::GetDayOfYear  
 この日付/時刻値で表される年間積算日を取得します。  
  
```
int GetDayOfYear() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値で表される年間積算日`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、年の日付を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値は 1 ~ 366 の範囲を 1 月 1 日に 1 を = です。  
  
 この値をクエリするその他のメンバー関数の詳細について`COleDateTime`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]  
  
##  <a name="gethour"></a>  COleDateTime::GetHour  
 この日付/時刻値で表される時間を取得します。  
  
```
int GetHour() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値で表される時間`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、時間を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値の 0 から 23 までの範囲です。  
  
 この値をクエリするその他のメンバー関数の詳細について`COleDateTime`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]  
  
##  <a name="getminute"></a>  COleDateTime::GetMinute  
 この日付/時刻値で表される分を取得します。  
  
```
int GetMinute() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値によって表される分`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、1 分間を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値の 0 から 59 までの範囲です。  
  
 この値をクエリするその他のメンバー関数の詳細について`COleDateTime`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>例  
 例を参照して[GetHour](#gethour)です。  
  
##  <a name="getmonth"></a>  COleDateTime::GetMonth  
 この日付/時刻値で表される月を取得します。  
  
```
int GetMonth() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値によって表される月`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、月を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値の 1 から 12 までの範囲です。  
  
 この値をクエリするその他のメンバー関数の詳細について`COleDateTime`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDay](#getday)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>例  
 例を参照して[GetDay](#getday)です。  
  
##  <a name="getsecond"></a>  COleDateTime::GetSecond  
 この日付/時刻値で表される秒を取得します。  
  
```
int GetSecond() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値によって表される秒`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、2 つ目を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値の 0 から 59 までの範囲です。  
  
> [!NOTE]
>  `COleDateTime`クラスはうるう秒をサポートしていません。  
  
 実装の詳細については`COleDateTime`、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
 この値をクエリするその他のメンバー関数の詳細について`COleDateTime`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>例  
 例を参照して[GetHour](#gethour)です。  
  
##  <a name="getstatus"></a>  「  
 状態を取得します (有効期間) の指定された`COleDateTime`オブジェクト。  
  
```
DateTimeStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この状態を返します`COleDateTime`値。 呼び出す場合は**GetStatus**上、`COleDateTime`オブジェクトを構築、既定値が返されます無効です。 呼び出す場合**GetStatus**上、`COleDateTime`は null に設定するコンス トラクターで初期化されたオブジェクト**GetStatus**は null を返します。 参照してください**解説**詳細についてはします。  
  
### <a name="remarks"></a>コメント  
 戻り値は、**返します**列挙内で定義されている型、`COleDateTime`クラスです。  
  
```  
enum DateTimeStatus  
{  
   error = -1,  
   valid = 0,  
   invalid = 1,    // Invalid date (out of range, etc.)  
   null = 2,       // Literally has no value  
};  
```  
  
 これらのステータス値の簡単な説明は、次の一覧を参照してください。  
  
- `COleDateTime::error` 日付/時刻値の一部を取得しようとしているときにエラーが発生したことを示します。  
  
- **COleDateTime::valid**ことを示しますこの`COleDateTime`オブジェクトは無効にします。  
  
- **COleDateTime::invalid**ことを示しますこの`COleDateTime`オブジェクトは無効です。 つまり、その値誤りがあります。  
  
- **COleDateTime::null**ことを示しますこの`COleDateTime`オブジェクトが null の場合は、このオブジェクトの値が指定されていないこと。 (これは"null"の「値を持たない、」C++ ではなくデータベース意味で**NULL**)。  
  
 状態、`COleDateTime`オブジェクトでは、次の場合。  
  
-   その値が設定されている場合、**バリアント**または`COleVariant`値を日付/時刻値に変換できませんでした。  
  
-   その値が設定されている場合、 `time_t`、 `SYSTEMTIME`、または`FILETIME`値を有効な日付/時刻値に変換できませんでした。  
  
-   その値が設定されている場合`SetDateTime`無効なパラメーター値を使用します。  
  
-   このオブジェクトが発生したため、オーバーフローまたはアンダー フロー代入演算操作中、つまり場合、`+=`または`-=`です。  
  
-   場合は、無効な値は、このオブジェクトに割り当てられました。  
  
-   このオブジェクトの状態に無効なを使用して明示的に設定された`SetStatus`です。  
  
 操作の詳細については、無効なメンバー関数は、次を参照してください状態を設定する場合があります。  
  
- [COleDateTime](#coledatetime)  
  
- [について](#setdatetime)  
  
- [演算子 +、-](#operator_add_-)  
  
- [演算子 + =、=](#operator_add_eq_-_eq)  
  
 境界の詳細については`COleDateTime`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]  
  
##  <a name="getyear"></a>  COleDateTime::GetYear  
 この日付/時刻値で表される年間を取得します。  
  
```
int GetYear() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 この値で表される年間`COleDateTime`オブジェクトまたは`COleDateTime::error`場合は、年を取得できませんでした。  
  
### <a name="remarks"></a>コメント  
 有効な戻り値の範囲 100 ~ 9999 の間、2 桁の年が含まれます。  
  
 この値をクエリするその他のメンバー関数の詳細について`COleDateTime`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 境界の詳細については`COleDateTime`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
### <a name="example"></a>例  
 例を参照して[GetDay](#getday)です。  
  
##  <a name="m_dt"></a>  COleDateTime::m_dt  
 基になる**日付**この構造体`COleDateTime`オブジェクト。  
  
```
DATE m_dt;
```  
  
### <a name="remarks"></a>コメント  
  
> [!CAUTION]
>  値を変更、**日付**この関数によって返されるポインターによってアクセスされるオブジェクトがこの値を変更`COleDateTime`オブジェクト。 この状態は変更されません`COleDateTime`オブジェクト。  
  
 実装の詳細については、**日付**オブジェクトは、「[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
##  <a name="m_status"></a>  COleDateTime::m_status  
 この状態を含む`COleDateTime`オブジェクト。  
  
```
DateTimeStatus m_status;
```  
  
### <a name="remarks"></a>コメント  
 このデータ メンバーの型は列挙型**返します**、内で定義されている、`COleDateTime`クラスです。 参照してください[は、「](#getstatus)詳細についてはします。  
  
> [!CAUTION]
>  このデータ メンバーは、高度なプログラミングに適しています。 インライン メンバー関数を使用する必要があります[GetStatus](#getstatus)と[SetStatus](#setstatus)です。 参照してください`SetStatus`の他の注意に関するこのデータ メンバーを明示的に設定します。  
  
##  <a name="operator_eq"></a>  COleDateTime::operator =  
 コピー、`COleDateTime`値。  
  
```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& udate) throw();
```  
  
### <a name="remarks"></a>コメント  
 これらのオーバー ロードされた代入演算子は、これに元の日付/時刻値をコピー`COleDateTime`オブジェクト。 これらのそれぞれの簡単な説明では、代入演算子のオーバー ロードされました。  
  
- **演算子 = = (** `dateSrc` **)** 値およびオペランドの状態は、これにコピーされます`COleDateTime`オブジェクト。  
  
- **演算子 = = (** *varSrc* **)** 場合の変換、[バリアント](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)値 (または[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクト) を日付/時刻 (`VT_DATE`) が成功すると、変換後の値がコピーにこの`COleDateTime`オブジェクトとその状態は、有効な設定ができます。 このオブジェクトの値が 0 (1899 年 12 月 30 日の午前 0 時) に設定は、変換が成功しなかった場合、その状態は無効にします。  
  
- **演算子 = = (** `dtSrc` **)** 、**日付**値がこれにコピー`COleDateTime`オブジェクトとその状態は、有効な設定です。  
  
- **演算子 = = (** `timeSrc` **)** 、`time_t`または **_ _time64_t**値が変換され、これにコピー`COleDateTime`オブジェクト。 変換が成功した場合は、このオブジェクトの状態が設定無効です。失敗した場合、設定されているかどうかが無効にします。  
  
- **演算子 = = (** *systimeSrc* **)** 、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)値が変換され、これにコピー`COleDateTime`オブジェクト。 変換が成功した場合は、このオブジェクトの状態が設定無効です。失敗した場合、設定されているかどうかが無効にします。  
  
- **演算子 = = (** `udate` **)** 、 **UDATE**値が変換され、これにコピー`COleDateTime`オブジェクト。 変換が成功した場合は、このオブジェクトの状態が設定無効です。失敗した場合、設定されているかどうかが無効にします。 A **UDATE**構造体は、「展開」の日付を表します。 関数を参照してください[VarDateFromUdate](http://msdn.microsoft.com/en-us/1c924ac5-b896-49e1-9ccf-825ac7a030c8)詳細についてはします。  
  
- **演算子 = = (** `filetimeSrc` **)** 、 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)値が変換され、これにコピー`COleDateTime`オブジェクト。 変換が成功した場合は、このオブジェクトの状態が設定無効です。それ以外の場合に設定されている無効にします。 `FILETIME` 世界協定時刻 (UTC) を使用して、ため、構造の UTC 時刻を渡した場合、結果をローカル時間に UTC 時刻から変換されますバリアント時刻として格納されます。 この動作は、Visual C 6.0 および Visual C .NET 2003 SP2 のものと同じです。 参照してください[ファイル時間](http://msdn.microsoft.com/library/windows/desktop/ms724290)詳細については、Windows SDK に含まれています。  
  
 詳細については、次を参照してください。、[バリアント](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)Windows SDK 内のエントリ。  
  
 詳細については、`time_t`データ型を参照してください、[時間](../../c-runtime-library/reference/time-time32-time64.md)で機能、*ランタイム ライブラリ リファレンス*です。  
  
 詳細については、次を参照してください。、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)と[FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Windows SDK 内の構造体。  
  
 境界の詳細については`COleDateTime`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
##  <a name="operator_add_-"></a>  COleDateTime::operator +、-  
 加算および減算**ColeDateTime**値。  
  
```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```  
  
### <a name="remarks"></a>コメント  
 `COleDateTime` オブジェクトは、絶対時刻を表します。 [しかし](../../atl-mfc-shared/reference/coledatetimespan-class.md)オブジェクトは相対時間を表します。 最初の 2 つの演算子を使用すると、加算し、減算、`COleDateTimeSpan`値から、`COleDateTime`値。 3 番目の演算子では、1 を減算することができます`COleDateTime`を譲渡して別の値、`COleDateTimeSpan`値。  
  
 結果の状態は null オペランドのいずれかの場合`COleDateTime`値は null です。  
  
 場合、結果として得られる`COleDateTime`値が許容される値、状態の境界の外側にある`COleDateTime`値が無効です。  
  
 オペランドのいずれかが有効ではなく、もう一方が null でない場合、その結果のステータス`COleDateTime`値が無効です。  
  
 **+** と**-** 場合演算子が評価されます、`COleDateTime`オブジェクトが設定を null にします。 参照してください[COleDateTime 関係演算子](#coledatetime_relational_operators)例についてはします。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数。  
  
 境界の詳細については`COleDateTime`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  COleDateTime::operator + =、=  
 加算および減算、 **ColeDateTime**これから値`COleDateTime`オブジェクト。  
  
```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>コメント  
 これらの演算子を使用すると、加算し、減算、`COleDateTimeSpan`値からこの`COleDateTime`です。 結果の状態は null オペランドのいずれかの場合`COleDateTime`値は null です。  
  
 場合、結果として得られる`COleDateTime`値が許容される値、この状態の境界の外側にある`COleDateTime`値が設定されて無効にします。  
  
 オペランドのいずれかが有効ではなくが null でないその他の場合、その結果のステータス`COleDateTime`値が無効です。  
  
 有効、無効、および null 状態の値の詳細については、次を参照してください。、[ついて](#m_status)メンバー変数。  
  
 **+=** と**-=** 場合演算子が評価されます、`COleDateTime`オブジェクトが設定を null にします。 参照してください[COleDateTime 関係演算子](#coledatetime_relational_operators)例についてはします。  
  
 境界の詳細については`COleDateTime`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
##  <a name="operator_date"></a>  COleDateTime::operator 日付  
 変換、 **ColeDateTime**値に、**日付**です。  
  
```
operator DATE() const throw();
```  
  
### <a name="remarks"></a>コメント  
 この演算子を返します、**日付**値がこれからコピーしたオブジェクト`COleDateTime`オブジェクト。 実装の詳細については、**日付**オブジェクトは、「[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
 **日付**場合にオペレーターがアサート、`COleDateTime`オブジェクトが設定を null にします。 参照してください[COleDateTime 関係演算子](#coledatetime_relational_operators)例についてはします。  
  
##  <a name="parsedatetime"></a>  COleDateTime::ParseDateTime  
 日付/時刻値を読み取るための文字列を解析します。  
  
```
bool ParseDateTime(  
 LPCTSTR lpszDate,
 DWORD dwFlags = 0,
 LCID lcid = LANG_USER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszDate`  
 解析するのには null で終わる文字列へのポインター。 詳細については、「解説」を参照してください。  
  
 `dwFlags`  
 ロケールの設定と解析のフラグを示します。 1 つ以上の次のフラグ:  
  
- **LOCALE_NOUSEROVERRIDE**カスタムのユーザー設定ではなく、システムの既定のロケール設定を使用します。  
  
- **VAR_TIMEVALUEONLY**解析中に、日付部分を無視します。  
  
- **VAR_DATEVALUEONLY**解析時に時刻部分を無視します。  
  
 `lcid`  
 変換を使用するロケール ID を示します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**かどうか、文字列が正常に変換された日付/時刻値をそれ以外の場合**false**です。  
  
### <a name="remarks"></a>コメント  
 文字列が日付/時刻を正常に変換された場合の値、この値`COleDateTime`オブジェクトが有効な値とする状態に設定します。  
  
> [!NOTE]
>  年の値は 100 ~ 9999 の間以内でなければなりません。  
  
 `lpszDate`パラメーターは、さまざまな形式を取ることができます。 たとえば、次の文字列には、許容される日付/時刻書式が含まれます。  
  
 `"25 January 1996"`  
  
 `"8:30:00"`  
  
 `"20:30:00"`  
  
 `"January 25, 1996 8:30:00"`  
  
 `"8:30:00 Jan. 25, 1996"`  
  
 `"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`  
  
 ロケール ID もに影響を与える文字列の形式が日付/時刻値に変換できるかどうかに注意してください。  
  
 場合、 **VAR_DATEVALUEONLY**時間が 0、または午前 0 時に値が設定されている時間。 場合、 **VAR_TIMEVALUEONLY**値が日付 0、つまり 1899 年 12 月 30日に設定された日付。  
  
 文字列が日付/時刻値に変換できませんでしたか数値オーバーフロー、この状態が発生しました`COleDateTime`オブジェクトが無効です。  
  
 境界との実装の詳細については`COleDateTime`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
##  <a name="setdate"></a>  COleDateTime::SetDate  
 この日付が設定`COleDateTime`オブジェクト。  
  
```
int SetDate(  
 int nYear,
 int nMonth,
 int nDay) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nYear`、`nMonth`、`nDay`  
 これにコピーされる日付の構成要素を示す`COleDateTime`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 場合は 0 の値`COleDateTime`オブジェクトが設定された正常です。 それ以外の場合、1 です。 この戻り値がに基づいて、**返します**列挙型。 詳細については、次を参照してください。、 [SetStatus](#setstatus)メンバー関数。  
  
### <a name="remarks"></a>コメント  
 日付は指定された値に設定します。 時間は、時間が 0、午前 0 時に設定されます。  
  
 パラメーターの値の範囲は次の表を参照してください。  
  
|パラメーター|境界|  
|---------------|------------|  
|`nYear`|100 - 9999|  
|`nMonth`|1 - 12|  
|`nDay`|0 - 31|  
  
 月の日がオーバーフローした場合は、次の月と月の正しい日付に変換されます/年がインクリメントされます。 0 の日付の値では、前の月の最終日を示します。 動作は同じ`SystemTimeToVariantTime`です。  
  
 このオブジェクトの状態に設定して、パラメーターで指定された日付の値が有効でない場合**COleDateTime::invalid**です。 使用する必要があります[GetStatus](#getstatus)の有効性を確認する、**日付**値し、を想定しないでくださいの値[m_dt](#m_dt)変更されません。  
  
 日付値の例を次に示します。  
  
|`nYear`|`nMonth`|`nDay`|[値]|  
|-------------|--------------|------------|-----------|  
|2000|2|29|2000 年 2 月 29日|  
|1776|7|4|1776 年 7 月 4 日|  
|1925|4|35|35 年 1925年 4 月 (無効な日付)|  
|10000|1|1|1 年 1 月 10000 (無効な日付)|  
  
 日付と時刻の両方を設定するを参照してください。 [COleDateTime::SetDateTime](#setdatetime)です。  
  
 この値を照会するメンバー関数の詳細について`COleDateTime`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 境界の詳細については`COleDateTime`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]  
  
##  <a name="setdatetime"></a>  COleDateTime::SetDateTime  
 この日時設定`COleDateTime`オブジェクト。  
  
```
int SetDateTime(  
 int nYear,
 int nMonth,
 int nDay,
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 これにコピーされる日付と時刻のコンポーネントを示す`COleDateTime`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 場合は 0 の値`COleDateTime`オブジェクトが設定された正常です。 それ以外の場合、1 です。 この戻り値がに基づいて、**返します**列挙型。 詳細については、次を参照してください。、 [SetStatus](#setstatus)メンバー関数。  
  
### <a name="remarks"></a>コメント  
 パラメーターの値の範囲は次の表を参照してください。  
  
|パラメーター|境界|  
|---------------|------------|  
|`nYear`|100 - 9999|  
|`nMonth`|1 - 12|  
|`nDay`|0 - 31|  
|`nHour`|0 - 23|  
|`nMin`|0 - 59|  
|`nSec`|0 - 59|  
  
 月の日がオーバーフローした場合は、次の月と月の正しい日付に変換されます/年がインクリメントされます。 0 の日付の値では、前の月の最終日を示します。 動作は同じ[SystemTimeToVariantTime](http://msdn.microsoft.com/en-us/d9d69521-9b33-4fc5-8a1c-929f216db450)です。  
  
 パラメーターで指定された日付または時刻の値が無効の場合、このオブジェクトの状態が無効ですし、このオブジェクトの値に設定する場合は変更されません。  
  
 次に時刻値の例をいくつかを示します。  
  
|`nHour`|`nMin`|`nSec`|[値]|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|無効|  
|9|60|0|無効|  
  
 日付値の例を次に示します。  
  
|`nYear`|`nMonth`|`nDay`|[値]|  
|-------------|--------------|------------|-----------|  
|1995|4|16|1995 年 4 月 15日|  
|1789|7|14|17 1789 年 7 月|  
|1925|2|30|無効|  
|10000|1|1|無効|  
  
 日付のみを設定するを参照してください。 [COleDateTime::SetDate](#setdate)です。 時刻のみを設定するを参照してください。 [COleDateTime::SetTime](#settime)です。  
  
 この値を照会するメンバー関数の詳細について`COleDateTime`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 境界の詳細については`COleDateTime`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
### <a name="example"></a>例  
 例を参照して[GetStatus](#getstatus)です。  
  
##  <a name="setstatus"></a>  COleDateTime::SetStatus  
 この状態を設定`COleDateTime`オブジェクト。  
  
```
void SetStatus(DateTimeStatus status) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *status*  
 この新しいステータス値`COleDateTime`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 *ステータス*パラメーターの値がによって定義された、**返します**列挙内で定義されている型、`COleDateTime`クラスです。 参照してください[は、「](#getstatus)詳細についてはします。  
  
> [!CAUTION]
>  この関数は、高度なプログラミング環境です。 この関数では、このオブジェクトのデータは変更されません。 状態を設定に使用されるほとんどの場合、`null`または**無効な**します。 なお、代入演算子 ([演算子 =](#eq)) と[について](#setdatetime)ソース値に基づいて、オブジェクトの状態を設定しないでください。  
  
### <a name="example"></a>例  
 例を参照して[GetStatus](#getstatus)です。  
  
##  <a name="settime"></a>  COleDateTime::SetTime  
 この時間を設定`COleDateTime`オブジェクト。  
  
```
int SetTime(  
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nHour`、`nMin`、`nSec`  
 これにコピーされる時コンポーネントを示す`COleDateTime`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 場合は 0 の値`COleDateTime`オブジェクトが設定された正常です。 それ以外の場合、1 です。 この戻り値がに基づいて、**返します**列挙型。 詳細については、次を参照してください。、 [SetStatus](#setstatus)メンバー関数。  
  
### <a name="remarks"></a>コメント  
 時間は、指定した値に設定されます。 日付は日付 0、つまり 1899 年 12 月 30日に設定します。  
  
 パラメーターの値の範囲は次の表を参照してください。  
  
|パラメーター|境界|  
|---------------|------------|  
|`nHour`|0 - 23|  
|`nMin`|0 - 59|  
|`nSec`|0 - 59|  
  
 パラメーターで指定された値が有効でない時間が無効ですし、このオブジェクトの値をこのオブジェクトの状態が設定されている場合は変更されません。  
  
 次に時刻値の例をいくつかを示します。  
  
|`nHour`|`nMin`|`nSec`|[値]|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|無効|  
|9|60|0|無効|  
  
 日付と時刻の両方を設定するを参照してください。 [COleDateTime::SetDateTime](#setdatetime)です。  
  
 この値を照会するメンバー関数の詳細について`COleDateTime`オブジェクト メンバー関数は、次を参照してください。  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 境界の詳細については`COleDateTime`、値は、記事を参照して[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
### <a name="example"></a>例  
 例を参照して[SetDate](#setdate)です。  
  
## <a name="see-also"></a>関連項目  
 [COleVariant クラス](../../mfc/reference/colevariant-class.md)   
 [CTime クラス](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan クラス](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)




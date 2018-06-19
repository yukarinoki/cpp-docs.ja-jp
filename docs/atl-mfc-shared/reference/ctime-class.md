---
title: CTime クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTime
- ATLTIME/ATL::CTime
- ATLTIME/ATL::CTime::CTime
- ATLTIME/ATL::CTime::Format
- ATLTIME/ATL::CTime::FormatGmt
- ATLTIME/ATL::CTime::GetAsDBTIMESTAMP
- ATLTIME/ATL::CTime::GetAsSystemTime
- ATLTIME/ATL::CTime::GetCurrentTime
- ATLTIME/ATL::CTime::GetDay
- ATLTIME/ATL::CTime::GetDayOfWeek
- ATLTIME/ATL::CTime::GetGmtTm
- ATLTIME/ATL::CTime::GetHour
- ATLTIME/ATL::CTime::GetLocalTm
- ATLTIME/ATL::CTime::GetMinute
- ATLTIME/ATL::CTime::GetMonth
- ATLTIME/ATL::CTime::GetSecond
- ATLTIME/ATL::CTime::GetTime
- ATLTIME/ATL::CTime::GetYear
- ATLTIME/ATL::CTime::Serialize64
dev_langs:
- C++
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ec195c7733255487b08f8b48379abe58e305f61
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366550"
---
# <a name="ctime-class"></a>CTime クラス
絶対時刻と日付を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CTime  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CTime::CTime](#ctime)|構築`CTime`さまざまな方法でオブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTime::Format](#format)|変換します、`CTime`オブジェクトを書式設定された文字列に、ローカル タイム ゾーンに基づきます。|  
|[CTime::FormatGmt](#formatgmt)|変換、`CTime`オブジェクトを書式設定された文字列に — UTC に基づきます。|  
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|格納されている時刻情報を変換、 `CTime` Win32 互換 DBTIMESTAMP 構造体へのオブジェクト。|  
|[CTime::GetAsSystemTime](#getassystemtime)|格納されている時刻情報を変換、 `CTime` Win32 互換オブジェクト[SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)構造体。|  
|[CTime::GetCurrentTime](#getcurrenttime)|作成、`CTime`を現在の時刻 (静的メンバー関数) を表すオブジェクト。|  
|[CTime::GetDay](#getday)|によって表される日を返します、`CTime`オブジェクト。|  
|[CTime::GetDayOfWeek](#getdayofweek)|によって表される週の日を返します、`CTime`オブジェクト。|  
|[CTime::GetGmtTm](#getgmttm)|分割、`CTime`オブジェクトをコンポーネントに — UTC に基づきます。|  
|[CTime::GetHour](#gethour)|によって表される時間を返します、`CTime`オブジェクト。|  
|[CTime::GetLocalTm](#getlocaltm)|分割、`CTime`オブジェクトをコンポーネントに — ローカル タイム ゾーンに基づきます。|  
|[CTime::GetMinute](#getminute)|によって表される分が返されます、`CTime`オブジェクト。|  
|[渡して](#getmonth)|によって表される月を返します、`CTime`オブジェクト。|  
|[CTime::GetSecond](#getsecond)|によって表される秒を返します、`CTime`オブジェクト。|  
|[CTime::GetTime](#gettime)|返します、 **_ _time64_t**値を指定された`CTime`オブジェクト。|  
|[CTime::GetYear](#getyear)|によって表される年を返します、`CTime`オブジェクト。|  
|[CTime::Serialize64](#serialize64)|またはアーカイブからデータをシリアル化します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 + -](#operator_add_-)|これらの演算子が加算および減算`CTimeSpan`と`CTime`オブジェクト。|  
|[演算子 + =、=](#operator_add_eq_-_eq)|これらの演算子が加算および減算、`CTimeSpan`オブジェクトからこの`CTime`オブジェクト。|  
|[演算子 =](#operator_eq)|代入演算子です。|  
|[演算子 = =、<, などです。](#ctime_comparison_operators)|比較演算子です。|  
  
## <a name="remarks"></a>コメント  
 `CTime` 基本クラスはありません。  
  
 `CTime` 値は、協定世界時 (グリニッジ標準時、GMT) には、世界協定時刻 (UTC) に基づいています。 参照してください[時間管理](../../c-runtime-library/time-management.md)については、タイム ゾーンを決定する方法です。  
  
 作成するときに、`CTime`オブジェクト、設定、`nDST`パラメーターを 0 にするか標準時では実際には、0 より大きい値をその夏時間が有効で、または C ランタイム ライブラリ コード最上に 0 より小さい値e かどうか (標準時) または夏時間が有効です。 `tm_isdst` は必須フィールドです。 かどうか設定されていない、その値は未定義とからの戻り値[mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)は予測できません。 場合`timeptr`前の呼び出しによって返される、tm 構造体を指す[asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)、 [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)、または[localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)、`tm_isdst`フィールドが含まれています、適切な値です。  
  
 コンパニオン クラス[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)、時間間隔を表します。  
  
 `CTime`と`CTimeSpan`クラスが派生させるために設計されていません。 サイズの仮想関数が存在しないため`CTime`と`CTimeSpan`オブジェクトは、厳密に 8 バイト。 ほとんどのメンバー関数はインラインです。  
  
> [!NOTE]
>  日付の上限は、12/31/3000 です。 下限値は 1970 年 1 月 1/12時 00分: 00 AM GMT です。  
  
 使用しての詳細については`CTime`、記事を参照して[日付と時刻](../../atl-mfc-shared/date-and-time.md)、および[時間管理](../../c-runtime-library/time-management.md)ランタイム ライブラリ リファレンスです。  
  
> [!NOTE]
>  `CTime`構造が MFC 8.0 に MFC 7.1 から変更します。 シリアル化する場合、`CTime`構造体を使用して、 `operator <<` MFC 8.0 またはそれ以降のバージョンでは、結果として得られるファイルは読み取れない MFC の以前のバージョン。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltime.h  
  
##  <a name="ctime_comparison_operators"></a>  CTime 比較演算子  
 比較演算子です。  
  
```  
bool operator==(CTime time) const throw(); 
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `time`  
 比較される `CTime` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 これらの演算子は 2 つの絶対時刻を比較し、 **true**条件の場合は true。 それ以外の場合**false**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]  
  
##  <a name="ctime"></a>  CTime::CTime  
 新たに作成`CTime`指定した時刻に初期化されるオブジェクト。  
  
```  
CTime() throw(); 
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts,int nDST = -1) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `timeSrc`  
 示します、`CTime`既に存在するオブジェクト。  
  
 `time`  
 A **_ _time64_t**時刻の値は、1970 年 1 月 1 日 UTC (秒数) の数です。 これが、現地時刻に調整されることに注意してください。 たとえば、ニューヨークにして作成した場合、 `CTime` 0 の場合のパラメーターを渡すことによってオブジェクト[渡して](#getmonth)12 が返されます。  

  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 新しいにコピーされる日付と時刻の値を示す`CTime`オブジェクト。  
  
 `nDST`  
 夏時間が有効になっているかどうかを示します。 次の 3 つの値のいずれかを持つことができます。  
  
- `nDST` 0Standard 時間に設定が有効です。  
  
- `nDST` 時刻が有効になって 0Daylight より大きい値に設定します。  
  
- `nDST` 0 the 既定よりも小さい値に設定します。 標準時間と夏時間のどちらが有効ではかどうかを自動的に計算します。  
  
 `wDosDate`, `wDosTime`  
 MS-DOS 日付と時刻の値は、日付/時刻値に変換され、新しいコピー`CTime`オブジェクト。  
  
 `st`  
 A [SYSTEMTIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d6609fff-1931-4818-8a26-f042630af0b0/locales/en-us)日付/時刻値に変換され、新しいコピーを構造`CTime`オブジェクト。  
  
 `ft`  
 A [FILETIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/979ce746-dc17-4147-89f8-41d05c5fcc5f/locales/en-us)日付/時刻値に変換され、新しいコピーを構造`CTime`オブジェクト。  
  
 dbts  
 現在の現地時刻を含む DBTIMESTAMP 構造体への参照。  
  
### <a name="remarks"></a>コメント  
 各コンス トラクターは、次に示します。  
  
- **CTime() です。** 構築、初期化されていない`CTime`オブジェクト。 このコンス トラクターを定義できます。`CTime`オブジェクトの配列。 使用する前に有効な値では、そのような配列を初期化する必要があります。  
  
- **CTime (const CTime (& a)) です。** 構築、`CTime`から別のオブジェクト`CTime`値。  
  
- **CTime (_ _time64_t) です。** 構築、`CTime`オブジェクトから、 **_ _time64_t**型です。 このコンス トラクターは、UTC 時刻が必要ですし、結果を格納する前にローカル時刻に結果を変換します。  
  
- **CTime (int, int,...)。** 構築、`CTime`各コンポーネントのローカル時刻要素オブジェクトは、次の範囲に制限します。  
  
    |コンポーネント|範囲|  
    |---------------|-----------|  
    |`nYear`|1970-3000|  
    |`nMonth`|1-12|  
    |`nDay`|1-31|  
    |`nHour`|0-23|  
    |`nMin`|0-59|  
    |`nSec`|0-59|  
  
     このコンス トラクターは、UTC への適切な変換です。 Microsoft Foundation Class ライブラリのデバッグ バージョン アサートの場合は 1 つまたは複数時コンポーネントの範囲外です。 呼び出しの前に引数を検証する必要があります。 このコンス トラクターには、現地時刻が必要です。  
  
- **CTime (WORD, 単語);** 構築、 `CTime` MS-DOS 日付と時刻の値は、指定したオブジェクト。 このコンス トラクターには、現地時刻が必要です。  
  
- **CTime (const SYSTEMTIME (& a)) です。** 構築、`CTime`オブジェクトから、`SYSTEMTIME`構造体。 このコンス トラクターには、現地時刻が必要です。  
  
- **CTime (const FILETIME (& a)) です。** 構築、`CTime`オブジェクトから、`FILETIME`構造体。 多くの場合は使用しません`CTime FILETIME`直接の初期化します。 使用する場合、`CFile`ファイルを操作するオブジェクト`CFile::GetStatus`経由のファイルのタイムスタンプを取得、`CTime`オブジェクトを初期化して、`FILETIME`構造体。 このコンス トラクターは、UTC に基づく、時間と想定し、結果を格納する前にローカル時刻に自動的に値に変換します。  
  
    > [!NOTE]
    >  コンス トラクターを使用して、 **DBTIMESTAMP**パラメーターは、OLEDB.h が含まれる場合にのみ使用できます。  
  
 詳細については、次を参照してください。、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)と[FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Windows SDK 内の構造。 参照してください、 [MS-DOS 日付と時刻](http://msdn.microsoft.com/library/windows/desktop/ms724503)Windows SDK 内のエントリ。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]  
  
##  <a name="format"></a>  CTime::Format  
 日付と時刻の値の書式設定された表現を作成するには、このメンバー関数を呼び出します。  
  
```  
CString Format(LPCTSTR pszFormat) const; 
CString Format(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `pszFormat`  
 書式文字列のような`printf`文字列の書式設定します。 割合に続くコードの書式設定 ( `%`) 署名は、対応する置き換え`CTime`コンポーネントです。 その他の文字書式指定文字列では、返される文字列に変更されずにコピーされます。 実行時の関数を参照して[strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)コードの書式設定の一覧についてはします。  
  
 `nFormatID`  
 この形式を識別する文字列の ID。  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)書式設定された時刻を格納しています。  
  
### <a name="remarks"></a>コメント  
 場合のこのステータス`CTime`戻り値は空の文字列は、オブジェクトが null です。  
  
 このメソッドは例外をスロー書式を設定する日付と時刻の値が範囲内にないから午前 0 時、1970 年 1 月 1 日の 3000 年 12 月 31 日を世界協定時刻 (UTC)。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]  
  
##  <a name="formatgmt"></a>  CTime::FormatGmt  
 これに対応する書式設定された文字列を生成`CTime`オブジェクト。  
  
```  
CString FormatGmt(LPCTSTR pszFormat) const; 
CString FormatGmt(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `pszFormat`  
 ような書式設定文字列を指定します、`printf`文字列の書式設定します。 実行時の関数を参照して[strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)詳細についてはします。  
  
 `nFormatID`  
 この形式を識別する文字列の ID。  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)書式設定された時刻を格納しています。  
  
### <a name="remarks"></a>コメント  
 時刻の値は変換されないと、(utc) に基づいて生成されます。  
  
 このメソッドは例外をスロー書式を設定する日付と時刻の値が範囲内にないから午前 0 時、1970 年 1 月 1 日の 3000 年 12 月 31 日を世界協定時刻 (UTC)。  
  
### <a name="example"></a>例  
 例を参照して[CTime::Format](#format)です。  
  
##  <a name="getasdbtimestamp"></a>  CTime::GetAsDBTIMESTAMP  
 格納されている時刻情報を変換するには、このメンバー関数を呼び出す、 `CTime` Win32 互換 DBTIMESTAMP 構造体へのオブジェクト。  
  
```  
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dbts`  
 現在の現地時刻を含む DBTIMESTAMP 構造体への参照。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 結果として得られる時刻を、参照されている `dbts` 構造体に格納します。 **DBTIMESTAMP**この関数によって初期化されたデータ構造が含まれ、**分数**メンバーが 0 に設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]  
  
##  <a name="getassystemtime"></a>  CTime::GetAsSystemTime  
 格納されている時刻情報を変換するには、このメンバー関数を呼び出す、 `CTime` Win32 互換オブジェクト[SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)構造体。  
  
```  
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *timeDest*  
 参照、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)の変換後の日付/時刻値を保持する構造体、`CTime`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は true。それ以外の場合は false。  
  
### <a name="remarks"></a>コメント  
 `GetAsSystemTime` 参照先の結果として得られる時刻を格納*timeDest*構造体。 `SYSTEMTIME`この関数によって初期化されたデータ構造が含まれ、 **wMilliseconds**メンバーが 0 に設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]  
  
##  <a name="getcurrenttime"></a>  CTime::GetCurrentTime  
 返します、`CTime`を現在の時刻を表すオブジェクト。  
  
```  
static CTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="remarks"></a>コメント  
 現在のシステム日付と時刻を世界協定時刻 (UTC) を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]  
  
##  <a name="getday"></a>  CTime::GetDay  
 によって表される日を返します、`CTime`オブジェクト。  
  
```  
int GetDay() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 1 ~ 31 の範囲内でのローカル時刻に基づき、月の日を返します。  
  
### <a name="remarks"></a>コメント  
 この関数が呼び出す`GetLocalTm`が、静的に割り当てられた内部バッファーを使用します。 このバッファー内のデータが他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]  
  
##  <a name="getdayofweek"></a>  CTime::GetDayOfWeek  
 によって表される週の日を返します、`CTime`オブジェクト。  
  
```  
int GetDayOfWeek() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 ローカル時刻に基づいて週の曜日を返します。1 = 日曜日、2 = 月曜日、土曜日を = 7 にします。  
  
### <a name="remarks"></a>コメント  
 この関数が呼び出す`GetLocalTm`バッファーの割り当てを使用して、内部静的にします。 このバッファー内のデータが他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]  
  
##  <a name="getgmttm"></a>  CTime::GetGmtTm  
 取得、**構造体 tm**これに含まれている時刻の分解を格納している`CTime`オブジェクト。  
  
```  
struct tm* GetGmtTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `ptm`  
 時間データを受け取るバッファーへのポインター。 このポインターがある場合**NULL**例外がスローされます。  
  
### <a name="return-value"></a>戻り値  
 入力では、によってへのポインター**構造体 tm**時にインクルード ファイルで定義されています。H. 参照してください[gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)構造体。  
  
### <a name="remarks"></a>コメント  
 `GetGmtTm` (utc) を返します。  
  
 `ptm` として `NULL` を使用することはできません。 これで、以前の動作に戻す場合`ptm`可能性があります`NULL`を静的に割り当てられた内部のバッファーを使用することを示す、未定義、`_SECURE_ATL`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]  
  
##  <a name="gethour"></a>  CTime::GetHour  
 によって表される時間を返します、`CTime`オブジェクト。  
  
```  
int GetHour() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 0 ~ 23 の範囲内でのローカル時刻に基づいて、時間を返します。  
  
### <a name="remarks"></a>コメント  
 この関数が呼び出す`GetLocalTm`バッファーの割り当てを使用して、内部静的にします。 このバッファー内のデータが他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]  
  
##  <a name="getlocaltm"></a>  CTime::GetLocalTm  
 取得、**構造体 tm**これに含まれている時刻の分解を含む`CTime`オブジェクト。  
  
```  
struct tm* GetLocalTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `ptm`  
 時間データを受け取るバッファーへのポインター。 このポインターがある場合**NULL**例外がスローされます。  
  
### <a name="return-value"></a>戻り値  
 入力では、によってへのポインター**構造体 tm**時にインクルード ファイルで定義されています。H. 参照してください[gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)構造体。  
  
### <a name="remarks"></a>コメント  
 `GetLocalTm` ローカル時刻を返します。  
  
 `ptm` として `NULL` を使用することはできません。 これで、以前の動作に戻す場合`ptm`可能性があります`NULL`を静的に割り当てられた内部のバッファーを使用することを示す、未定義、`_SECURE_ATL`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]  
  
##  <a name="getminute"></a>  CTime::GetMinute  
 によって表される分が返されます、`CTime`オブジェクト。  
  
```  
int GetMinute() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 0 ~ 59 の範囲内でのローカル時刻に基づいて、分を返します。  
  
### <a name="remarks"></a>コメント  
 この関数が呼び出す`GetLocalTm`バッファーの割り当てを使用して、内部静的にします。 このバッファー内のデータが他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 例を参照して[GetHour](#gethour)です。  
  
##  <a name="getmonth"></a>  渡して  
 によって表される月を返します、`CTime`オブジェクト。  
  
```  
int GetMonth() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 1 ~ 12 の範囲内でのローカル時刻に基づいて、月を返します (1 年 1 月 =)。  
  
### <a name="remarks"></a>コメント  
 この関数が呼び出す`GetLocalTm`バッファーの割り当てを使用して、内部静的にします。 このバッファー内のデータが他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 例を参照して[GetDay](#getday)です。  
  
##  <a name="getsecond"></a>  CTime::GetSecond  
 によって表される秒を返します、`CTime`オブジェクト。  
  
```  
int GetSecond() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 返します、2 つ目は、0 ~ 59 の範囲内でのローカル時刻に基づいて。  
  
### <a name="remarks"></a>コメント  
 この関数が呼び出す`GetLocalTm`バッファーの割り当てを使用して、内部静的にします。 このバッファー内のデータが他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 例を参照して[GetHour](#gethour)です。  
  
##  <a name="gettime"></a>  CTime::GetTime  
 返します、 **_ _time64_t**値を指定された`CTime`オブジェクト。  
  
```  
__time64_t GetTime() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 **GetTime**現在間の秒数を返す`CTime`オブジェクトと 1970 年 1 月 1 日です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]  
  
##  <a name="getyear"></a>  CTime::GetYear  
 によって表される年を返します、`CTime`オブジェクト。  
  
```  
int GetYear();
```  
  
### <a name="return-value"></a>戻り値  
 年、月 1 日の範囲内でのローカル時刻に基づいて返します 1,1970、2038 年 1 月 18日 (包括) にします。  
  
### <a name="remarks"></a>コメント  
 この関数が呼び出す`GetLocalTm`バッファーの割り当てを使用して、内部静的にします。 このバッファー内のデータが他の呼び出しによって上書きされます`CTime`メンバー関数。  
  
### <a name="example"></a>例  
 例を参照して[GetDay](#getday)です。  
  
##  <a name="operator_eq"></a>  CTime::operator =  
 代入演算子です。  
  
```  
CTime& operator=(__time64_t time) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `time`  
 新しい日付/時刻値。  
  
### <a name="return-value"></a>戻り値  
 更新された`CTime`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 このオーバー ロードされた代入演算子は、これに、元の時刻をコピー`CTime`オブジェクト。 時刻を内部ストレージ、`CTime`オブジェクトはタイム ゾーンに依存しません。 タイム ゾーンの変換は、代入時に必要ではありません。  
  
##  <a name="operator_add_-"></a>  CTime::operator +、-  
 これらの演算子が加算および減算`CTimeSpan`と`CTime`オブジェクト。  
  
```  
CTime operator+(CTimeSpan timeSpan) const throw(); 
CTime operator-(CTimeSpan timeSpan) const throw(); 
CTimeSpan operator-(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 *TimeSpan*  
 `CTimeSpan`加算または減算するオブジェクト。  
  
 `time`  
 `CTime`減算されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 A`CTime`または`CTimeSpan`操作の結果を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CTime` オブジェクトを表す絶対時間、`CTimeSpan`オブジェクトは、相対的な時間を表します。 最初の 2 つの演算子を使用すると、加算し、減算`CTimeSpan`オブジェクトとの間`CTime`オブジェクト。 3 番目の演算子では、1 を減算することができます`CTime`を譲渡して別のオブジェクト、`CTimeSpan`オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  CTime::operator + =、=  
 これらの演算子が加算および減算、`CTimeSpan`オブジェクトからこの`CTime`オブジェクト。  
  
```  
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CTimeSpan`加算または減算するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新された`CTime`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 これらの演算子を使用すると、加算し、減算、`CTimeSpan`オブジェクトからこの`CTime`オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]  
  
##  <a name="serialize64"></a>  CTime::Serialize64  
  
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
 [asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime_s、_ftime32_s、_ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)   
 [gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [strftime、wcsftime、_strftime_l、_wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [CTimeSpan クラス](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)



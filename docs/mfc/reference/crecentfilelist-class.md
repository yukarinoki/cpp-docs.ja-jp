---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
dev_langs:
- C++
helpviewer_keywords:
- CRecentFileList [MFC], CRecentFileList
- CRecentFileList [MFC], Add
- CRecentFileList [MFC], GetDisplayName
- CRecentFileList [MFC], GetSize
- CRecentFileList [MFC], ReadList
- CRecentFileList [MFC], Remove
- CRecentFileList [MFC], UpdateMenu
- CRecentFileList [MFC], WriteList
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d1dc8b636d0c97bc220f9c7f0f1e1cd165369e0
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079017"
---
# <a name="crecentfilelist-class"></a>関数クラス
MRU ファイル リストのコントロールをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CRecentFileList  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRecentFileList::CRecentFileList](#crecentfilelist)|`CRecentFileList` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRecentFileList::Add](#add)|MRU ファイル リストにファイルを追加します。|  
|[CRecentFileList::GetDisplayName](#getdisplayname)|MRU ファイル名の表示にメニューの表示名を提供します。|  
|[CRecentFileList::GetSize](#getsize)|MRU ファイル リスト内のファイルの数を取得します。|  
|[CRecentFileList::ReadList](#readlist)|MRU ファイル リストをレジストリから読み取りまたはします。INI ファイルです。|  
|[CRecentFileList::Remove](#remove)|MRU ファイル リストからファイルを削除します。|  
|[CRecentFileList::UpdateMenu](#updatemenu)|MRU ファイル リストのメニューの表示を更新します。|  
|[CRecentFileList::WriteList](#writelist)|レジストリから MRU ファイル リストを書き込み、または。INI ファイルです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CRecentFileList::operator](#operator_at)|返します、`CString`指定位置にあるオブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 ファイルを追加または MRU ファイル リストから削除されることができます、ファイルの一覧を読み取りまたはレジストリに書き込まれることができますか。INI ファイル、および MRU ファイル リストを表示するメニューを更新することができます。  
  
 最近使用したメニュー項目の詳細については、次を参照してください。  
  
-   サポート技術情報の記事 Q243751: HOWTO: の MFC アプリケーションの最近使用したメニュー項目コマンド ハンドラーの追加  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CRecentFileList`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxadv.h  
  
##  <a name="add"></a>  CRecentFileList::Add  
 最近使用した (MRU) ファイルの一覧にファイルを追加します。  
  
```  
virtual void Add(LPCTSTR lpszPathName);

 
virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

 
void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

 
void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

 
void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```  
  
### <a name="parameters"></a>パラメーター  
 *終了*  
 一覧に追加するパス名を指定します。  
  
 *lpszAppID*  
 アプリケーションのアプリケーション ユーザー モデル ID を指定します。  
  
 *pItem*  
 一覧に追加するシェル項目へのポインターを指定します。  
  
 *pLink*  
 一覧に追加するシェル リンクへのポインターを指定します。  
  
 *pidl*  
 最近使ったドキュメント フォルダーに追加する必要がありますシェル項目の IDLIST を指定します。  
  
### <a name="remarks"></a>Remarks  
 ファイル名を MRU 一覧の先頭に追加されます。 MRU 一覧にファイル名が既に存在する場合は、最上位に移動されます。  
  
##  <a name="crecentfilelist"></a>  CRecentFileList::CRecentFileList  
 `CRecentFileList` オブジェクトを構築します。  
  
```  
CRecentFileList(
    UINT nStart,  
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntryFormat,  
    int nSize,  
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```  
  
### <a name="parameters"></a>パラメーター  
 *開始*  
 (最も最近使用した) MRU ファイル リストのメニュー表示内の番号のオフセットします。  
  
 *大文字、小文字*  
 レジストリまたはアプリケーションのセクションの名前を指します。MRU ファイル リスト INI ファイルは読み取りや書き込みをします。  
  
 *lpszEntryFormat*  
 レジストリまたはアプリケーションの格納されているエントリの名前に使用する書式指定文字列を指します。INI ファイルです。  
  
 *nSize*  
 MRU ファイル リスト内のファイルの最大数。  
  
 *nMaxDispLen*  
 MRU ファイル リスト内のファイル名のメニューの表示に使用できる文字の最大長。  
  
### <a name="remarks"></a>Remarks  
 書式指定文字列を指す*lpszEntryFormat* "%d"MRU の各項目のインデックスの置換に使用されるを含める必要があります。 たとえば、書式指定文字列は`"file%d"`このという名前を付けると、エントリは`file0`、`file1`のようにします。  
  
##  <a name="getdisplayname"></a>  CRecentFileList::GetDisplayName  
 MRU 一覧のメニューの表示で使用するため、MRU ファイル リスト内のファイルの表示名を取得します。  
  
```  
virtual BOOL GetDisplayName(
    CString& strName,  
    int nIndex,  
    LPCTSTR lpszCurDir,  
    int nCurDir,  
    BOOL bAtLeastName = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *strName*  
 名前は、MRU ファイルのメニューの一覧に表示されるファイルの完全パス。  
  
 *nIndex*  
 MRU ファイル リスト内のファイルの 0 から始まるインデックス。  
  
 *lpszCurDir*  
 現在のディレクトリを保持している文字列。  
  
 *nCurDir*  
 現在のディレクトリの文字列の長さです。  
  
 *bAtLeastName*  
 ゼロ以外の場合を示します、ファイルのベース名を返すことを最大表示長を超えている場合でも (として渡される、 *nMaxDispLen*パラメーターを`CRecentFileList`コンス トラクター)。  
  
### <a name="return-value"></a>戻り値  
 **FALSE**かどうかがファイル名指定したインデックス位置にない最近使用した (MRU) ファイルの一覧です。  
  
### <a name="remarks"></a>Remarks  
 ファイルが現在のディレクトリ内にある場合は、関数は、ままディレクトリ表示をオフにします。 ファイル名が長すぎる場合、ディレクトリと拡張機能が削除されています。 しない限り、空の文字列に表示名を設定するファイル名が長すぎても場合、 *bAtLeastName*は 0 以外。  
  
##  <a name="getsize"></a>  CRecentFileList::GetSize  
 MRU ファイル リスト内のファイルの数を取得します。  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のファイルの数は、MRU ファイル リストを最も最近使用します。  
  
##  <a name="operator_at"></a>  CRecentFileList::operator  
 オーバー ロードされた、添字 ( `[]`) 演算子は、1 つを返します`CString`内の 0 から始まるインデックスによって指定された*nIndex*です。  
  
```  
CString& operator[ ](int nindex);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 0 から始まるインデックス、`CString`一連の`CString`s。  
  
##  <a name="readlist"></a>  CRecentFileList::ReadList  
 最近使用した (MRU) からレジストリまたはアプリケーションのファイルの一覧を読み取ります。INI ファイルです。  
  
```  
virtual void ReadList();
```  
  
##  <a name="remove"></a>  CRecentFileList::Remove  
 MRU ファイル リストからファイルを削除します。  
  
```  
virtual void Remove(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 最近使用した (MRU) ファイルの一覧から削除するファイルの 0 から始まるインデックス。  
  
##  <a name="updatemenu"></a>  CRecentFileList::UpdateMenu  
 MRU ファイル リストのメニューの表示を更新します。  
  
```  
virtual void UpdateMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 *対応付けられました。*  
 ポインター、 [CCmdUI](../../mfc/reference/ccmdui-class.md)最近使用した (MRU) ファイルのリスト メニューのオブジェクト。  
  
##  <a name="writelist"></a>  CRecentFileList::WriteList  
 最近使用した (MRU) ファイルの一覧に、レジストリまたはアプリケーションを書き込みます。INI ファイルです。  
  
```  
virtual void WriteList();
```  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)




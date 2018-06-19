---
title: Ccommand::open |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CCommand.Open
- ATL::CCommand::Open
- CCommand.Open
- CCommand::Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: 4c9b8f31-faf3-452d-9a29-3d3e5f54d6f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 82b87ad01bf072358042e9af7170afea1f7d4e88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092090"
---
# <a name="ccommandopen"></a>CCommand::Open
実行し、必要に応じて、コマンドをバインドします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCWSTR wszCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  


HRESULT Open(const CSession& session,  
   LPCSTR szCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  


HRESULT Open(const CSession& session,  
   INT szCommand = NULL,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  


HRESULT Open(DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   bool bBind = true,  
   ULONG ulPropSets = 0) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `session`  
 [in]コマンドを実行するセッションです。  
  
 `wszCommand`  
 [in]コマンドを実行するには、Unicode 文字列として渡されます。 指定できます**NULL**を使用する場合`CAccessor`に渡される値から、コマンドが取得される場合、 [DEFINE_COMMAND](../../data/oledb/define-command.md)マクロです。 参照してください[icommand::execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx)で、 *OLE DB プログラマーズ リファレンス*詳細についてはします。  
  
 `szCommand`  
 [in]同じ`wszCommand`ことを除き、このパラメーターは、ANSI コマンド文字列を取得します。 このメソッドの 4 番目の形式は、NULL 値をとることができます。 詳細については、このトピックの後半の「解説」を参照してください。  
  
 *pPropSet*  
 [in]配列へのポインター [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)プロパティと設定する値を含む構造体。 参照してください[プロパティ セットとプロパティ グループ](https://msdn.microsoft.com/en-us/library/ms713696.aspx)で、 *OLE DB プログラマーズ リファレンス*Windows SDK にします。  
  
 `pRowsAffected`  
 [入力/出力]コマンドによって影響を受ける行の数が返されるメモリへのポインター。 場合 *\*pRowsAffected*は**NULL**行の数は返されません。 それ以外の場合、**開く**設定 *`pRowsAffected`次の条件に従って。  
  
|If|Then|  
|--------|----------|  
|**CParamSets**要素の`pParams`が 1 より大きい|*`pRowsAffected` すべての実行で指定されたパラメーター セットによって影響を受ける行の合計数を表します。|  
|影響を受けた行の数が使用可能です|*`pRowsAffected` -1 に設定されます。|  
|コマンドが更新されない、削除、または行の挿入|*`pRowsAffected` 定義されていません。|  
  
 `guidCommand`  
 [in]コマンド テキストを解析中に、構文と使用するプロバイダーの一般的な規則を指定する GUID です。 参照してください[ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx)と[icommandtext::setcommandtext](https://msdn.microsoft.com/en-us/library/ms709757.aspx)で、 *OLE DB プログラマーズ リファレンス*詳細についてはします。  
  
 `bBind`  
 [in]コマンドを実行中の後に自動的にバインドするかどうかを指定します。 既定値は**true**、それが原因で、コマンドを自動的に連結されます。 設定`bBind`に**false**手動でバインドできるように、コマンドの自動に連結します。 (手動バインディングは、OLAP のユーザーに特に関心があるは) です。  
  
 `ulPropSets`  
 [in]数[DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)に渡された構造体、 *pPropSet*引数。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 最初の 3 つ**開く**セッションをとり、コマンドを作成し、コマンド、必要に応じて、任意のパラメーターをバインドします。  
  
 最初のフォーム**開く**Unicode コマンド文字列を受け取り、既定値はありません。  
  
 2 番目のフォーム**開く**は ANSI コマンド文字列および既定値はありません (既存の ANSI アプリケーションの旧バージョンと互換性のための指定) を取得します。  
  
 3 番目の形式の**開く**により、NULL の場合、型のためにコマンド文字列`int`で、既定値は NULL です。 呼び出すのために用意されて`Open(session, NULL);`または`Open(session);`型の NULL であるため`int`です。 このバージョンが必要です、アサートする、`int`パラメーターを NULL にします。  
  
 4 番目のフォームを使用して**開く**コマンドを作成しておくと、1 つを実行する[準備](../../data/oledb/ccommand-prepare.md)と複数回実行します。  
  
> [!NOTE]
>  **開いている**呼び出し**Execute**、さらに呼び出す`GetNextResult`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CCommand クラス](../../data/oledb/ccommand-class.md)
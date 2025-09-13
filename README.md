https://raw.githubusercontent.com/almeidarxs/RenHub/main/RenHub.lua
-- RenHub Blox Fruits 2025 | Menu principal + funções Beta + whitelist + AFK universal

-- Configuração da whitelist: só você testa funções beta!
local whitelist = {
    ["almeidarxs"] = true, -- Seu nome do Roblox, adicione outros se quiser liberar pra amigos!
}

local executor = identifyexecutor and identifyexecutor() or "Desconhecido"

local player = game.Players.LocalPlayer

-- Sistema AFK universal para todos executores
if game:GetService("Players").LocalPlayer then
    game:GetService("Players").LocalPlayer.Idled:connect(function()
        game:GetService("VirtualUser"):Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
    end)
end

-- Funções beta do menu
local betaFunctions = {
    {name = "Auto Awakening & Mastery Farm 2025", desc = "Beta - Farm automático de maestria/frutas do update."},
    {name = "Evento Mundial Tracker & Auto TP", desc = "Beta - TP para eventos globais do update."},
    {name = "Auto Fruit Swap & Combos 2025", desc = "Beta - Troca/frutas combos automáticos."},
    {name = "Market & Trade Sniper", desc = "Beta - Snipe de mercado/troca rara."},
    {name = "Auto Farm Pets/Summons", desc = "Beta - Farm para pets/summons do update."},
    {name = "Server Hop Inteligente", desc = "Beta - Vai para servidor novo, sem script users."},
}

-- Funções normais (exemplo)
local normalFunctions = {
    {name = "Auto Farm Boss", desc = "Farm automático de bosses."},
    {name = "Auto Bounty Hop", desc = "Farm automático de bounty."},
    {name = "Auto Sea Event", desc = "Farm automático de eventos do mar."},
    {name = "Aimlock", desc = "Aim automático para ataques."},
    {name = "Music Menu", desc = "Tocar músicas + Server Hop Inteligente (Beta)."},
}

-- Função para mostrar menu
function showMenu()
    print("=== RENHUB BLOX FRUITS 2025 ===")
    print("Executor detectado: " .. executor)
    print("Suporte para todos executores: Vulcano, Velocity, Rolex, Delta, Fluxus, Arceus X, Hydra, Kiwi, KRNL, etc.")
    print("Sistema AFK ativado! Seu farm está seguro.\n")
    print("Funções Normais:")
    for _, func in ipairs(normalFunctions) do
        print("- " .. func.name .. ": " .. func.desc)
    end
    print("\nFunções Beta (Atualizadas para 2025):")
    if whitelist[player.Name] then
        for _, func in ipairs(betaFunctions) do
            print("[BETA] " .. func.name .. ": " .. func.desc .. " [Liberado para Dono]")
        end
    else
        for _, func in ipairs(betaFunctions) do
            print("[BETA] " .. func.name .. ": " .. func.desc .. " (Bloqueado - Função restrita, aguardando liberação)")
        end
    end
    print("\nPara liberar funções beta para outros membros, adicione o nome deles na whitelist.")
    print("Para dúvidas ou suporte, entre em contato com o dono.")
end

showMenu()

-- Aqui você pode criar a lógica das funções, usando pcall e métodos universais para evitar crash/kick.
-- Exemplo de função universal que não causa kick:
function safeFarmBoss()
    pcall(function()
        -- Sua lógica de farm aqui, sempre usando waits, checks, sem loops infinitos
    end)
end

-- Exemplo de Server Hop Inteligente (Beta)
function smartServerHop()
    pcall(function()
        print("Server Hop Inteligente [BETA]: Procurando servidores novos e limpos...")
        -- Aqui entra a lógica de busca de servidores, só liberada para whitelist
        -- Você pode integrar com APIs de server list/executor em updates futuros
    end)
end

-- Exemplo de chamada da função beta (só você pode usar)
if whitelist[player.Name] then
    -- Você pode testar as funções beta chamando elas aqui, por exemplo:
    -- smartServerHop()
end
-- Loader universal para RenHub Blox Fruits 2025
local url = "https://raw.githubusercontent.com/almeidarxs/RenHub/main/RenHub.lua" -- Troque pelo seu link no GitHub, LittyRuby, Pastebin
loadstring(game:HttpGet(url))()

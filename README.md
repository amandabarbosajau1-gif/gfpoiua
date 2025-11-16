-- Variável onde será guardada a posição salva
local posicaoSalva = nil

-- Pegando o jogador local
local player = game.Players.LocalPlayer

-- Pegando os botões na interface
local gui = script.Parent
local botaoSalvar = gui:WaitForChild("BotaoSalvar")
local botaoTP = gui:WaitForChild("BotaoTP")


-- BOTÃO 1: SALVAR POSIÇÃO
botaoSalvar.MouseButton1Click:Connect(function()
    local char = player.Character
    if char and char:FindFirstChild("HumanoidRootPart") then
        posicaoSalva = char.HumanoidRootPart.CFrame
        print("Posição salva!")
    end
end)


-- BOTÃO 2: TELEPORTAR PARA POSIÇÃO SALVA
botaoTP.MouseButton1Click:Connect(function()
    local char = player.Character
    if posicaoSalva and char and char:FindFirstChild("HumanoidRootPart") then
        char.HumanoidRootPart.CFrame = posicaoSalva
        print("Teleportado!")
    end
end)

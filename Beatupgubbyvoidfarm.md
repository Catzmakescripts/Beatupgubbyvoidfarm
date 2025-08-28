-- ✅ Configuración
getgenv().VoidLoop = true   -- true = encendido | false = apagado
getgenv().Delay = 0.01       -- segundos de espera entre ejecuciones

-- ✅ Bucle
spawn(function()
    while getgenv().VoidLoop do
        local args = {
            vector.create(-3.625243663787842, 7.7213454246521, -0.001983236987143755)
        }

        game:GetService("ReplicatedStorage")
            :WaitForChild("Networking")
            :WaitForChild("Server")
            :WaitForChild("RemoteEvents")
            :WaitForChild("DamageEvents")
            :WaitForChild("VoidDamage")
            :FireServer(unpack(args))

        task.wait(getgenv().Delay)
    end
end)

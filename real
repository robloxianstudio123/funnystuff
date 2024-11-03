local MathPlusPlus=(function()
    if not isfile("mathplusplus.luau") then
    writefile("mathplusplus.luau",[[local module = {
	phi = 1.6180339887,
	e = 2.718281828459,
	G = 6.673*10^-11,
	
	naturalLog = function(exp)
		return math.log(exp, 2.718281828459)
	end,
	bound = function(min,max,value)
		return (-max+value)/(-max + min)
	end,
	derivative = function(x,dx, func)
		return (func(x + dx) - func(x))/dx
	end,
	ellipse = function(minor,major,t)
		return {math.cos(2*t*math.pi - math.pi) * major, math.sin(2*t*math.pi - math.pi) * minor}
	end,
	sigmoid = function(z)
		return 1/(1 + 2.718281828459^-z)
	end,
	quadratic = function(a,b,c,t)
		return a*(t^2)+(b*t)+c
	end,
	integral = function(a, b, dx, func)
		local sum = 0
		for n=a,b,dx do
			sum += func(n)
		end
		return sum*dx
	end,
	sum = function(a,b, func)
		local sum = 0
		for i=a,b,1 do
			sum += func(i)
		end
		return sum
	end,
	prod = function(a,b, func)
		local sum = a
		for i=a+1,b,1 do
			sum *= func(i)
		end
		return sum
	end,
	lerp = function(a,b,t)
		return a+(b-a)*t
	end,
	quadBezier = function(timeStep, control1, control2, control3)
		return (1-timeStep)^2 * control1 + 2*(1-timeStep) * timeStep * control2 + timeStep^2 * control3
	end,
	cubicBezier = function(timeStep, control1, control2, control3, control4)
		return (1-timeStep)^3 * control1 + 3*(1-timeStep)^2 * control2 + 3*(1-timeStep) * timeStep^2*control2 + timeStep^3 * control4
	end,
	eucDist = function(a,b,state)
		if state == 2 then
			return math.sqrt(((a.X - b.X)^2 + (a.Y - b.Y)^2))
		elseif state == 3 then
			return math.sqrt(((a.X - b.X)^2 + (a.Y - b.Y)^2 + (a.Z - b.Z)^2))
		else
			error("out of bound dimensions, must specify 2d or 3d (2 or 3)")
		end
	end,
	manHatDist = function(a,b,state)
		if state == 2 then
			return math.abs(a.X - b.X) + math.abs(a.Y - b.Y)
		elseif state == 3 then
			return math.abs(a.X - b.X) + math.abs(a.Y - b.Y) + math.abs(a.Z - b.Z)
		else
			error("out of bound dimensions, must specify 2d or 3d (2 or 3)")
		end
	end,
	chebDist = function(a,b,state)
		if state == 2 then
			return math.max(math.abs(a.X - b.X), math.abs(a.Y - b.Y))
		elseif state == 3 then
			return math.max(math.abs(a.X - b.X), math.abs(a.Y - b.Y), math.abs(a.Z - b.Z))
		else
			error("out of bound dimensions, must specify 2d or 3d (2 or 3)")
		end
	end,
	reflect = function(normal, dir)
		return dir-2*(dir:Dot(normal))*normal
	end,
	mat4x4 = function(components)
		local matrix = {{},{},{},{}}
		for i1 = 1, 4 do
			matrix[1][i1] = components[0+i1]
		end
		for i2 = 1, 4 do
			matrix[2][i2] = components[4+i2]
		end
		for i3 = 1, 4 do
			matrix[3][i3] = components[8+i3]
		end
		for i4 = 1, 4 do
			matrix[4][i4] = components[12+i4]
		end
		return matrix
	end,
}
return module]])
else
    return loadstring(readfile("mathplusplus.luau"))()
end
end)
return MathPlusPlus()
